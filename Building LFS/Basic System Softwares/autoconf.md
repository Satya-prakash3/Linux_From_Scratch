The Autoconf package contains programs for producing shell scripts that can automatically configure source code.

1. Extraction

	tar -xvf autoconf-2.72.tar.xz 
	cd autoconf-2.72

2. Building

	time { ./configure --prefix=/usr && make && make check && make install; }
