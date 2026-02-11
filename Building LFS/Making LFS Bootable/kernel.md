The Linux package contains the Linux kernel.

This is the main kernerl the great linux kernel we will compile it here

1. Extraction

    tar -xvf linux-6.16.1.tar.xz
    cd linux-6.16.1

2. Prepare for compilation

    make mrproper
    make defconfig (For default configuration)
    make menuconfig (Follow the lfs book for further instructions https://www.linuxfromscratch.org/lfs/view/stable/chapter10/kernel.html )

    make (Run this after costumizing and selectibg all the drivers)

    make modules_install

    cp -iv arch/x86/boot/bzImage /boot/vmlinuz-6.16.1-lfs-12.4

    cp -iv System.map /boot/System.map-6.16.1

    cp -iv .config /boot/config-6.16.1

    cp -r Documentation -T /usr/share/doc/linux-6.16.1

    chown -R 0:0 ../linux-6.16.1

    install -v -m755 -d /etc/modprobe.d
    cat > /etc/modprobe.d/usb.conf << "EOF"
    # Begin /etc/modprobe.d/usb.conf

    install ohci_hcd /sbin/modprobe ehci_hcd ; /sbin/modprobe -i ohci_hcd ; true
    install uhci_hcd /sbin/modprobe ehci_hcd ; /sbin/modprobe -i uhci_hcd ; true

    # End /etc/modprobe.d/usb.conf
    EOF
