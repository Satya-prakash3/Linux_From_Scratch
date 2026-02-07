Here we will install the binutils package.

The Binutils package contains a linker, an assembler, and other tools for handling object files.

1. First we will extract the package
    tar -xvf binutils-2.45.tar.xz
    cd binutils-2.45.tar.xz

2. The Binutils documentation recommends building Binutils in a dedicated build directory
    mkdir build 
    cd build

    time {
        ../configure --prefix=$LFS/tools \
             --with-sysroot=$LFS \
             --target=$LFS_TGT   \
             --disable-nls       \
             --enable-gprofng=no \
             --disable-werror    \
             --enable-new-dtags  \
             --enable-default-hash-style=gnu
             && make
             && make install; 
    }
