The Grep package contains programs for searching through the contents of files.

1. Extraction
	tar -xvf grep-3.12.tar.xz
	cd grep-3.12

2. Building
	time { ./configure --prefix=/usr               --host=$LFS_TGT             --build=$(./build-aux/config.guess) && make && make DESTDIR=$LFS install; }
