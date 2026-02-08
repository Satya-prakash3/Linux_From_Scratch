The Libtool package contains the GNU generic library support script. It makes the use of shared libraries simpler with a consistent, portable interface.

1. Extraction
	
	tar -xvf libtool-2.5.4.tar.xz
	cd libtool-2.5.4

2. Building
	
	time { ./configure --prefix=/usr && make && make check && make install; }
	rm -fv /usr/lib/libltdl.a


