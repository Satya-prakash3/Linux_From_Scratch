The Tar package provides the ability to create tar archives as well as perform various other kinds of archive manipulation. Tar can be used on previously created archives to extract files, to store additional files, or to update or list files which were already stored.

1. Extraction
	
	tar -xvf tar-1.35.tar.xz
	cd tar-1.35

2. Building

	FORCE_UNSAFE_CONFIGURE=1  \
./configure --prefix=/usr
	
	make
	make check
	make install
	make -C doc install-html docdir=/usr/share/doc/tar-1.35

