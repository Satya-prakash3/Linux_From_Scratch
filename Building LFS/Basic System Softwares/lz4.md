Lz4 is a lossless compression algorithm, providing compression speed greater than 500 MB/s per core. It features an extremely fast decoder, with speed in multiple GB/s per core. Lz4 can work with Zstandard to allow both algorithms to compress data faster.

1. Extraction
	tar -xvf lz4-1.10.0.tar.gz 
	cd lz4-1.10.0

2. Building
	make BUILD_STATIC=no PREFIX=/usr
	make -j1 check
	make BUILD_STATIC=no PREFIX=/usr install


