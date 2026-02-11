The Procps-ng package contains programs for monitoring processes.

1. Extraction
	
	tar -xvf procps-ng-4.0.5.tar.xz 
	cd procps-ng-4.0.5

2. Building

	time { ./configure --prefix=/usr                                       --docdir=/usr/share/doc/procps-ng-4.0.5             --disable-static                                    --disable-kill                                      --enable-watch8bit && make; }
	chown -R tester .
	su tester -c "PATH=$PATH make check"

	make install

