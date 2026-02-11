The Groff package contains programs for processing and formatting text and images.

1. Extraction

	tar -xvf groff-1.23.0.tar.gz
	cd groff-1.23.0

2. Building

	PAGE=<paper_size> ./configure --prefix=/usr (<paper_size> will be A4)
	make
	make check
	make install

