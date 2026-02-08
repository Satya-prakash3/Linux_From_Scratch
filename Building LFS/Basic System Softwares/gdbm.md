The GDBM package contains the GNU Database Manager. It is a library of database functions that uses extensible hashing and works like the standard UNIX dbm. The library provides primitives for storing key/data pairs, searching and retrieving the data by its key and deleting a key along with its data.

1. Extraction
		
	tar -xvf gdbm-1.26.tar.gz
	cd gdbm-1.26

2. Building

	time { ./configure --prefix=/usr                --disable-static             --enable-libgdbm-compat && make && make check && make install; }
