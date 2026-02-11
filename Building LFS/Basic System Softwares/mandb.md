The Man-DB package contains programs for finding and viewing man pages.

1. Extraction

	tar -xvf man-db-2.13.1.tar.xz
	cd man-db-2.13.1

2. Building

	time { ./configure --prefix=/usr                                     --docdir=/usr/share/doc/man-db-2.13.1             --sysconfdir=/etc                                 --disable-setuid                                  --enable-cache-owner=bin                          --with-browser=/usr/bin/lynx                      --with-vgrind=/usr/bin/vgrind                     --with-grap=/usr/bin/grap                         --with-systemdtmpfilesdir=                        --with-systemdsystemunitdir= && make; }
	make check
	make install
