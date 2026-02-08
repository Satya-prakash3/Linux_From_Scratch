The GMP package contains math libraries. These have useful functions for arbitrary precision arithmetic.

1. Extraction
	tar -xvf gmp-6.3.0.tar.xz
	cd gmp-6.3.0

2. Building
	sed -i '/long long t1;/,+1s/()/(...)/' configure
	time { ./configure --prefix=/usr                --enable-cxx                 --disable-static             --docdir=/usr/share/doc/gmp-6.3.0 && make && make html; }
	
	make check 2>&1 | tee gmp-check-log
	awk '/# PASS:/{total+=$3} ; END{print total}' gmp-check-log (Ensure atleast 199 checks are passed if not then you need to verify and solve it)
	
	make install
	make install-html

	
	
