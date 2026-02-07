Currently the whole /mnt/lfs/* is owned by lfs user that only exists in host system. If the directories and files under $LFS are kept as they are, they will be owned by a user ID without a corresponding account. This is dangerous because a user account created later could get this same user ID and would own all the files under $LFS, thus exposing these files to possible malicious manipulation.

1. Exit the lfs user
    exit
    check in root if $LFS is there or not if not 
    export LFS=/mnt/lfs

    Now change the ownership of the folder to root
    chown --from lfs -R root:root $LFS/{usr,var,etc,tools}
    case $(uname -m) in
    x86_64) chown --from lfs -R root:root $LFS/lib64 ;;
    esac

2. Preparing the virtual kernel file system
    User spaceapplications utilize various virtual file systems  to communicate with the kernel.
    These file systems are virtual have no disk usage completely in memory.
    We will create these file systems here 
    mkdir -pv $LFS/{dev,proc,sys,run}
    These file systems must be mounted to be accessed by applications inside chroot environmnet.

3. Mounting and Populating /dev
    Mostly distros will automatically mount the devtmpfs while booting, in this case we can rely on kernel and mount a devtmpfs in /dev and wait for kernel to populate it 
    But for safer side we will populate the /dev directory by bind mounting it will make a directory subtree or a file visible at some other location.
    We are doing it incase the host doesnot auto populate the /dev or have different mechanism.
    The bind mount will mirror the hosts /dev directoryinto $LFS/dev regardless how the hosts manages them.
    mount -v --bind /dev $LFS/dev

4. Mounting virtual kerenl file systems
    mount -vt devpts devpts -o gid=5,mode=0620 $LFS/dev/pts
    mount -vt proc proc $LFS/proc
    mount -vt sysfs sysfs $LFS/sys
    mount -vt tmpfs tmpfs $LFS/run

    if [ -h $LFS/dev/shm ]; then
    install -v -d -m 1777 $LFS$(realpath /dev/shm)
        else
    mount -vt tmpfs -o nosuid,nodev tmpfs $LFS/dev/shm
        fi

5. Entering chroot environment
    chroot "$LFS" /usr/bin/env -i   \
    HOME=/root                  \
    TERM="$TERM"                \
    PS1='(lfs chroot) \u:\w\$ ' \
    PATH=/usr/bin:/usr/sbin     \
    MAKEFLAGS="-j$(nproc)"      \
    TESTSUITEFLAGS="-j$(nproc)" \
    /bin/bash --login

6. Creating the Directories
    It is time to create the full directory structure in the LFS file system.
    mkdir -pv /{boot,home,mnt,opt,srv}

    mkdir -pv /etc/{opt,sysconfig}
    mkdir -pv /lib/firmware
    mkdir -pv /media/{floppy,cdrom}
    mkdir -pv /usr/{,local/}{include,src}
    mkdir -pv /usr/lib/locale
    mkdir -pv /usr/local/{bin,lib,sbin}
    mkdir -pv /usr/{,local/}share/{color,dict,doc,info,locale,man}
    mkdir -pv /usr/{,local/}share/{misc,terminfo,zoneinfo}
    mkdir -pv /usr/{,local/}share/man/man{1..8}
    mkdir -pv /var/{cache,local,log,mail,opt,spool}
    mkdir -pv /var/lib/{color,misc,locate}

    ln -sfv /run /var/run
    ln -sfv /run/lock /var/lock

    install -dv -m 0750 /root
    install -dv -m 1777 /tmp /var/tmp
7. Creating Essential Files and symlinks
    1. Historically, Linux maintained a list of the mounted file systems in the file /etc/mtab. Modern kernels maintain this list internally and expose it to the user via the /proc filesystem. To satisfy utilities that expect to find /etc/mtab, create the following symbolic link:
        ln -sv /proc/self/mounts /etc/mtab
    
    2. Create a basic /etc/hosts file to be referenced in some test suites, and in one of Perl's configuration files as well:
        cat > /etc/hosts << EOF
        127.0.0.1  localhost $(hostname)
        ::1        localhost
        EOF

    3. Here we will create the /etc/passwd file and add user root and some neccessary users to it 
        (This will create the /etc/passwd file)
        cat > /etc/passwd << "EOF"
        root:x:0:0:root:/root:/bin/bash
        bin:x:1:1:bin:/dev/null:/usr/bin/false
        daemon:x:6:6:Daemon User:/dev/null:/usr/bin/false
        messagebus:x:18:18:D-Bus Message Daemon User:/run/dbus:/usr/bin/false
        uuidd:x:80:80:UUID Generation Daemon User:/dev/null:/usr/bin/false
        nobody:x:65534:65534:Unprivileged User:/dev/null:/usr/bin/false
        EOF
        
        (This will create the /etc/groups file)
        cat > /etc/group << "EOF"
        root:x:0:
        bin:x:1:daemon
        sys:x:2:
        kmem:x:3:
        tape:x:4:
        tty:x:5:
        daemon:x:6:
        floppy:x:7:
        disk:x:8:
        lp:x:9:
        dialout:x:10:
        audio:x:11:
        video:x:12:
        utmp:x:13:
        cdrom:x:15:
        adm:x:16:
        messagebus:x:18:
        input:x:24:
        mail:x:34:
        kvm:x:61:
        uuidd:x:80:
        wheel:x:97:
        users:x:999:
        nogroup:x:65534:
        EOF

    4. Now we will create a temporary user for testing
        echo "tester:x:101:101::/home/tester:/bin/bash" >> /etc/passwd
        echo "tester:x:101:" >> /etc/group
        install -o tester -d /home/tester

    5. To remove "I have no name!" prompt start a new shell
        exec /usr/bin/bash --login

    6. Now we will create some neccessary log files
        touch /var/log/{btmp,lastlog,faillog,wtmp}
        chgrp -v utmp /var/log/lastlog
        chmod -v 664  /var/log/lastlog
        chmod -v 600  /var/log/btmp

8. Now we will build some additional temporary tools

9. After building we will clean up
    1. First, remove the currently installed documentation files to prevent them from ending up in the final system, and to save about 35 MB:
        rm -rf /usr/share/{info,man,doc}/*

    2. Second, on a modern Linux system, the libtool .la files are only useful for libltdl. No libraries in LFS are loaded by libltdl, and it's known that some .la files can cause BLFS package failures. Remove those files now:
        find /usr/{lib,libexec} -name \*.la -delete

    3. The current system size is now about 3 GB, however the /tools directory is no longer needed. It uses about 1 GB of disk space. Delete it now:
        rm -rf /tools

10. Backup 
    It's always good to take backup at this stage in case something goes wrong we can revert bak
    exit the chroot environment
    exit
    mountpoint -q $LFS/dev/shm && umount $LFS/dev/shm
    umount $LFS/dev/pts
    umount $LFS/{sys,proc,run,dev} 
    
    cd $LFS
    tar -cJpf $HOME/lfs-temp-tools-12.4.tar.xz .