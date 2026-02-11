The Gawk package contains programs for manipulating text files.

1. Extraction
	
	tar -xvf gawk-5.3.2.tar.xz
	cd gawk-5.3.2

2. Building

	sed -i 's/extras//' Makefile.in
	./configure --prefix=/usr
	
	make
	chown -R tester .

	su tester -c "PATH=$PATH make check"
	rm -f /usr/bin/gawk-5.3.2
	make install

	ln -sv gawk.1 /usr/share/man/man1/awk.1
	install -vDm644 doc/{awkforai.txt,*.{eps,pdf,jpg}} -t /usr/share/doc/gawk-5.3.2

