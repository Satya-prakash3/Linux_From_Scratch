The Sed package contains a stream editor.

1. Extraction
	tar -xvf sed-4.9.tar.xz
	cd sed-4.9

2. Building
	time { ./configure --prefix=/usr               --host=$LFS_TGT             --build=$(./build-aux/config.guess) && make && make DESTDIR=$LFS install; }	
