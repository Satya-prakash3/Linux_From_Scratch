The File package contains a utility for determining the type of a given file or files.

1. Extraction

	tar -xvf file-5.46.tar.gz
	cd file-5.46

2. Building

	mkdir build 
	pushd build
  ../configure --disable-bzlib      \
               --disable-libseccomp \
               --disable-xzlib      \
               --disable-zlib
  make
popd
	time { ./configure --prefix=/usr --host=$LFS_TGT --build=$(./config.guess) && make FILE_COMPILE=$(pwd)/build/src/file && make DESTDIR=$LFS install; }

	rm -v $LFS/usr/lib/libmagic.la

