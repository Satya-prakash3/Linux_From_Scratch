The Patch package contains a program for modifying or creating files by applying a “patch” file typically created by the diff program.

1. Extraction
	tar -xvf patch-2.8.tar.xz
	cd patch-2.8

2. Building
	time { ./configure --prefix=/usr               --host=$LFS_TGT             --build=$(build-aux/config.guess) && make && make DESTDIR=$LFS install; }
