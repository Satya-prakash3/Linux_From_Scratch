The Gzip package contains programs for compressing and decompressing files.

1. Extraction
	tar -xvf gzip-1.14.tar.xz
	cd gzip-1.14

2. Building
	time { ./configure --prefix=/usr --host=$LFS_TGT && make && make DESTDIR=$LFS install; }

