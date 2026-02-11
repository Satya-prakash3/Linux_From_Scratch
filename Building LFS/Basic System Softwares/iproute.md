The IPRoute2 package contains programs for basic and advanced IPV4-based networking.

1. Etraction
	
	tar -xvf iproute2-6.16.0.tar.xz
	cd iproute2-6.16.0

2. Building
	
	sed -i /ARPD/d Makefile
	rm -fv man/man8/arpd.8

	make NETNS_RUN_DIR=/run/netns
	make SBINDIR=/usr/sbin install

	install -vDm644 COPYING README* -t /usr/share/doc/iproute2-6.16.0

