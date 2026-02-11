The Util-linux package contains miscellaneous utility programs. Among them are utilities for handling file systems, consoles, partitions, and messages.

1. Extraction
	
	tar -xvf util-linux-2.41.1.tar.xz
	cd util-linux-2.41.1

2. Building
	
	time { ./configure --bindir=/usr/bin                 --libdir=/usr/lib                 --runstatedir=/run                --sbindir=/usr/sbin               --disable-chfn-chsh               --disable-login                   --disable-nologin                 --disable-su                      --disable-setpriv                 --disable-runuser                 --disable-pylibmount              --disable-liblastlog2             --disable-static                  --without-python                  --without-systemd                 --without-systemdsystemunitdir                    ADJTIME_PATH=/var/lib/hwclock/adjtime             --docdir=/usr/share/doc/util-linux-2.41.1 && make; }

	touch /etc/fstab
	chown -R tester .
	su tester -c "make -k check"

	make install
	
