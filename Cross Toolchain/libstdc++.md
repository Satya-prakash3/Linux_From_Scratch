Libstdc++ is the standard C++ library. It is needed to compile C++ code (part of GCC is written in C++), but we had to defer its installation when we built gcc-pass1 because Libstdc++ depends on Glibc, which was not yet available in the target directory.

1. Extraction
     tar -xvf gcc-15.2.0.tar.xz
     cd gcc-15.2.0.tar.xz

2. Building 
    mkdir -v build
    cd build

    time { ../libstdc++-v3/configure      \
    --host=$LFS_TGT            \
    --build=$(../config.guess) \
    --prefix=/usr              \
    --disable-multilib         \
    --disable-nls              \
    --disable-libstdcxx-pch    \
    --with-gxx-include-dir=/tools/$LFS_TGT/include/c++/15.2.0 && make && make DESTDIR=$LFS install; }

    rm -v $LFS/usr/lib/lib{stdc++{,exp,fs},supc++}.la
