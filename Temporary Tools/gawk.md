The Gawk package contains programs for manipulating text files.

1. Extraction
	tar -xvf gawk-5.3.2.tar.xz
	cd gawk-5.3.2

2. Building
	sed -i 's/extras//' Makefile.in
	time { ./configure --prefix=/usr               --host=$LFS_TGT             --build=$(build-aux/config.guess) && make && make DESTDIR=$LFS install; }
