The Automake package contains programs for generating Makefiles for use with Autoconf.

1. Extraction
	
	tar -xvf automake-1.18.1.tar.xz
	cd automake-1.18.1

2. Building
	
	./configure --prefix=/usr --docdir=/usr/share/doc/automake-1.18.1

	make
	make -j$(($(nproc)>4?$(nproc):4)) check
	make install

