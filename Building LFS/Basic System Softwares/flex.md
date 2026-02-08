The Flex package contains a utility for generating programs that recognize patterns in text.

1. Extraction
	tar -xvf flex-2.6.4.tar.gz
	cd flex-2.6.4

2. Building
	time { ./configure --prefix=/usr             --docdir=/usr/share/doc/flex-2.6.4             --disable-static && make && make check && make install; }
	ln -sv flex   /usr/bin/lex
	ln -sv flex.1 /usr/share/man/man1/lex.1
