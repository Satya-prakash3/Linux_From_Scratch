The MPFR package contains functions for multiple precision math.

1. Extraction
	
	tar -xvf mpfr-4.2.2.tar.xz
	cd mpfr-4.2.2

2. Building

	time { ./configure --prefix=/usr                    --disable-static                 --enable-thread-safe             --docdir=/usr/share/doc/mpfr-4.2.2 && make && make html; }
	make check

	make install
	make install-html

