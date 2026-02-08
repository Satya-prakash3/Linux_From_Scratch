Libelf is a library for handling ELF (Executable and Linkable Format) files.

1. Extraction

	tar -xvf elfutils-0.193.tar.bz2 
	elfutils-0.193

2. Building

	time { ./configure --prefix=/usr                    --disable-debuginfod             --enable-libdebuginfod=dummy && make; }

	make check
	make -C libelf install
	install -vm644 config/libelf.pc /usr/lib/pkgconfig
	
	rm /usr/lib/libelf.a
	
