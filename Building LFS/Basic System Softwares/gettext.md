The Gettext package contains utilities for internationalization and localization. These allow programs to be compiled with NLS (Native Language Support), enabling them to output messages in the user's native language.

1. Extraction

	tar -xvf gettext-0.26.tar.xz
	cd gettext-0.26

2. Building

	time { ./configure --prefix=/usr                --disable-static             --docdir=/usr/share/doc/gettext-0.26 && make && make check; }
	make install

	chmod -v 0755 /usr/lib/preloadable_libintl.so

