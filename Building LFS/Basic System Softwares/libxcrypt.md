The Libxcrypt package contains a modern library for one-way hashing of passwords.

1. Extraction

	tar -xvf libxcrypt-4.4.38.tar.xz
	cd libxcrypt-4.4.38

2. Building

	time { ./configure --prefix=/usr                            --enable-hashes=strong,glibc             --enable-obsolete-api=no                 --disable-static                         --disable-failure-tokens && make; }
	make check
	make install
