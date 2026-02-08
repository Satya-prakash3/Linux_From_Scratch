The Expat package contains a stream oriented C library for parsing XML.

1. Extraction
	tar -xvf expat-2.7.1.tar.xz 
	cd expat-2.7.1

2. Building

	time { ./configure --prefix=/usr                --disable-static             --docdir=/usr/share/doc/expat-2.7.1 && make && make check && make install; }
	install -v -m644 doc/*.{html,css} /usr/share/doc/expat-2.7.1

