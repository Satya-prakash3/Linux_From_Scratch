The Psmisc package contains programs for displaying information about running processes.

1. Extraction
	
	tar -xvf psmisc-23.7.tar.xz 
	cd psmisc-23.7

2. Building
	
	time { ./configure --prefix=/usr && make && make check && make install; }
