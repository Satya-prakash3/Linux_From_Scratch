The Diffutils package contains programs that show the differences between files or directories.

1. Extraction

	tar -xvf diffutils-3.12.tar.xz
	cd diffutils-3.12

2. Building

	time { ./configure --prefix=/usr && make && make check && make install; }
