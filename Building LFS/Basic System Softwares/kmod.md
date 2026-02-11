The Kmod package contains libraries and utilities for loading kernel modules

1. Extraction

	tar -xvf kmod-34.2.tar.xz
	cd kmod-34.2

2. Building
	
	mkdir -v build
	cd build

	meson setup --prefix=/usr ..    \
            --buildtype=release \
            -D manpages=false

	ninja 
	ninja install
