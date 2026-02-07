The Gettext package contains utilities for internationalization and localization. These allow programs to be compiled with NLS (Native Language Support), enabling them to output messages in the user's native language.

1. Extraction
	tar -xvf gettext-0.26.tar.xz
	cd gettext-0.26

2. Building
	time { ./configure --disable-shared && make; }
	cp -v gettext-tools/src/{msgfmt,msgmerge,xgettext} /usr/bin	

