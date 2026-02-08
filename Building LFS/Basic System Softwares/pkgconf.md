The pkgconf package is a successor to pkg-config and contains a tool for passing the include path and/or library paths to build tools during the configure and make phases of package installations.

1. Extraction
	tar -xvf pkgconf-2.5.1.tar.xz
	cd pkgconf-2.5.1

2. Building
	time { ./configure --prefix=/usr                --disable-static             --docdir=/usr/share/doc/pkgconf-2.5.1 && make && make install; }
	ln -sv pkgconf   /usr/bin/pkg-config
	ln -sv pkgconf.1 /usr/share/man/man1/pkg-config.1
