The Bc package contains an arbitrary precision numeric processing language.

1. Extraction
	tar -xvf bc-7.0.3.tar.xz
	cd bc-7.0.3

2. Building
	CC='gcc -std=c99' ./configure --prefix=/usr -G -O3 -r
	time { make && make test && make install; }
