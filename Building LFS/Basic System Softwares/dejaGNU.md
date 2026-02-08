The DejaGnu package contains a framework for running test suites on GNU tools. It is written in expect, which itself uses Tcl (Tool Command Language).

1. Extraction
	tar -xvf dejagnu-1.6.3.tar.gz
	cd dejagnu-1.6.3

2. Building
	mkdir -v build
	cd build

	time { ../configure --prefix=/usr; makeinfo --html --no-split -o doc/dejagnu.html ../doc/dejagnu.texi; makeinfo --plaintext       -o doc/dejagnu.txt  ../doc/dejagnu.texi && make check && make install; }
	
	install -v -dm755  /usr/share/doc/dejagnu-1.6.3
	install -v -m644   doc/dejagnu.{html,txt} /usr/share/doc/dejagnu-1.6.3	
