The Linux API Headers (in linux-6.16.1.tar.xz) expose the kernel's API for use by Glibc.

1. Extraction 
    tar -xvf linux-6.16.1.tar.xz

2. building
    make mrproper
    make headers
    find usr/include -type f ! -name '*.h' -delete
    cp -rv usr/include $LFS/usr
