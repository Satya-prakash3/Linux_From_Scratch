The Intltool is an internationalization tool used for extracting translatable strings from source files.

1. Extraction
	
	tar -xvf intltool-0.51.0.tar.gz
	cd intltool-0.51.0

2. Building

	sed -i 's:\\\${:\\\$\\{:' intltool-update.in

	./configure --prefix=/usr
	make
	make check
	make install

	install -v -Dm644 doc/I18N-HOWTO /usr/share/doc/intltool-0.51.0/I18N-HOWTO

