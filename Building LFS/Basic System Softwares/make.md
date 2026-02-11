The Make package contains a program for controlling the generation of executables and other non-source files of a package from source files.

1. Extraction

	tar -xvf make-4.4.1.tar.gz
	cd make-4.4.1

2. Building

	./configure --prefix=/usr
	make

	chown -R tester .
	su tester -c "PATH=$PATH make check"

	make install
