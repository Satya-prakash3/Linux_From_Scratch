The Attr package contains utilities to administer the extended attributes of filesystem objects.

1. Extraction
	tar -xvf attr-2.5.2.tar.gz
	cd attr-2.5.2

2. Building
	time { ./configure --prefix=/usr                 --disable-static              --sysconfdir=/etc             --docdir=/usr/share/doc/attr-2.5.2 && make; }
	
	make check
	make install
