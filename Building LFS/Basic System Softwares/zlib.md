The Zlib package contains compression and decompression routines used by some programs.

1. Extraction
	tar -xvf zlib-1.3.1.tar.gz
	cd zlib-1.3.1

2. Building
	time { ./configure --prefix=/usr && make && make check && make install; }

	rm -fv /usr/lib/libz.a

