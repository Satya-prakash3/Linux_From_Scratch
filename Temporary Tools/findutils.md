The Findutils package contains programs to find files. Programs are provided to search through all the files in a directory tree and to create, maintain, and search a database (often faster than the recursive find, but unreliable unless the database has been updated recently). Findutils also supplies the xargs program, which can be used to run a specified command on each file selected by a search.

1. Extraction
	tar -xvf findutils-4.10.0.tar.xz
	cd findutils-4.10.0

2. Building
	time { ./configure --prefix=/usr                               --localstatedir=/var/lib/locate             --host=$LFS_TGT                             --build=$(build-aux/config.guess) && make && make DESTDIR=$LFS install; }

