The Binutils package contains a linker, an assembler, and other tools for handling object files.

1. Extraction
	tar -xvf binutils-2.45.tar.xz
	cd binutils-2.45

2. Building
	mkdir -v build
	cd build

	time { ../configure --prefix=/usr                    --sysconfdir=/etc                --enable-ld=default              --enable-plugins                 --enable-shared                  --disable-werror                 --enable-64-bit-bfd              --enable-new-dtags               --with-system-zlib               --enable-default-hash-style=gnu && make tooldir=/usr; }
	
	grep '^FAIL:' $(find -name '*.log')

	time { make tooldir=/usr install; }
	
	rm -rfv /usr/lib/lib{bfd,ctf,ctf-nobfd,gprofng,opcodes,sframe}.a \
        /usr/share/doc/gprofng/
