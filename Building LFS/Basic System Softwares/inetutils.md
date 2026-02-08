The Inetutils package contains programs for basic networking.

1. Extraction
		
	tar -xvf inetutils-2.6.tar.xz
	cd inetutils-2.6

2. Building

	sed -i 's/def HAVE_TERMCAP_TGETENT/ 1/' telnet/telnet.c

	time { ./configure --prefix=/usr                    --bindir=/usr/bin                --localstatedir=/var             --disable-logger                 --disable-whois                  --disable-rcp                    --disable-rexec                  --disable-rlogin                 --disable-rsh                    --disable-servers && make && make check && make install; }

	mv -v /usr/{,s}bin/ifconfig

