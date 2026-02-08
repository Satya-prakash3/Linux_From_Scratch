Gperf generates a perfect hash function from a key set.

1. Extraction
	
	tar -xvf gperf-3.3.tar.gz 
	cd gperf-3.3

2. Building

	time { ./configure --prefix=/usr --docdir=/usr/share/doc/gperf-3.3 && make && make check && make install; }

