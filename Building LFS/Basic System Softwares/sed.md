The Sed package contains a stream editor.

1. Extraction

	tar -xvf sed-4.9.tar.xz
	cd sed-4.9

2. Building

	time { ./configure --prefix=/usr && make && make html; }
	chown -R tester .

	su tester -c "PATH=$PATH make check"

	make install

	install -d -m755           /usr/share/doc/sed-4.9
	install -m644 doc/sed.html /usr/share/doc/sed-4.9
	
