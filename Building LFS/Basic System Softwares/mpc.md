The MPC package contains a library for the arithmetic of complex numbers with arbitrarily high precision and correct rounding of the result.

1. Extraction
	tar -xvf mpc-1.3.1.tar.gz
	cd mpc-1.3.1

2. Building
	time { ./configure --prefix=/usr                --disable-static             --docdir=/usr/share/doc/mpc-1.3.1 && make && make html; }

	make check
	make install
	make install-html
