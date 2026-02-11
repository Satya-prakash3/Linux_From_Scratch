Grub is a powerful bGRUB works by writing data to the first physical track of the hard disk. This area is not part of any file system. The programs there access GRUB modules in the boot partition. The default location is /boot/grub/.oot manager for linux

grub-install /dev/vda (The vda depends on the hosts partiton )

    cat > /boot/grub/grub.cfg << "EOF"
    # Begin /boot/grub/grub.cfg
    set default=0
    set timeout=5

    insmod part_gpt
    insmod ext2
    set root=(hd0,2)
    set gfxpayload=1024x768x32

    menuentry "GNU/Linux, Linux 6.16.1-lfs-12.4" {
            linux   /boot/vmlinuz-6.16.1-lfs-12.4 root=/dev/sda2 ro
    }
    EOF



This is the end of our journey of LINUX from scratch

