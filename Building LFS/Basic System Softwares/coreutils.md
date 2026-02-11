The Coreutils package contains the basic utility programs needed by every operating system.

1. Extraction

	tar -xvf coreutils-9.7.tar.xz
	cd coreutils-9.7

2. Building

	patch -Np1 -i ../coreutils-9.7-upstream_fix-1.patch

	patch -Np1 -i ../coreutils-9.7-i18n-1.patch

	autoreconf -fv
	automake -af

	FORCE_UNSAFE_CONFIGURE=1 ./configure \
            --prefix=/usr            \
            --enable-no-install-program=kill,uptime

	make
	make NON_ROOT_USERNAME=tester check-root

	groupadd -g 102 dummy -U tester
	chown -R tester . 
	su tester -c "PATH=$PATH make -k RUN_EXPENSIVE_TESTS=yes check" \
   < /dev/null
	
	groupdel dummy
	make installmv -v /usr/bin/chroot /usr/sbin
	mv -v /usr/share/man/man1/chroot.1 /usr/share/man/man8/chroot.8
	sed -i 's/"1"/"8"/' /usr/share/man/man8/chroot.8

