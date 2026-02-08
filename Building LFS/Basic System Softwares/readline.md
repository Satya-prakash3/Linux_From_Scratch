The Readline package is a set of libraries that offer command-line editing and history capabilities.

1. Extraction
	tar -xvf readline-8.3.tar.gz
	cd readline-8.3

2. Buidling
	sed -i '/MV.*old/d' Makefile.in
	sed -i '/{OLDSUFF}/c:' support/shlib-install

	sed -i 's/-Wl,-rpath,[^ ]*//' support/shobj-conf

	time { ./configure --prefix=/usr                --disable-static             --with-curses                --docdir=/usr/share/doc/readline-8.3 && make SHLIB_LIBS="-lncursesw" && make install; }

	install -v -m644 doc/*.{ps,pdf,html,dvi} /usr/share/doc/readline-8.3

