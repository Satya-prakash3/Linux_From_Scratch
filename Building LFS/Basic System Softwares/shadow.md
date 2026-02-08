The Shadow package contains programs for handling passwords in a secure way.

1. Extraction
	
	tar -xvf shadow-4.18.0.tar.xz
	cd shadow-4.18.0

2. Building
	
	sed -i 's/groups$(EXEEXT) //' src/Makefile.in
	find man -name Makefile.in -exec sed -i 's/groups\.1 / /'   {} \;
	find man -name Makefile.in -exec sed -i 's/getspnam\.3 / /' {} \;
	find man -name Makefile.in -exec sed -i 's/passwd\.5 / /'   {} \;
	
	sed -e 's:#ENCRYPT_METHOD DES:ENCRYPT_METHOD YESCRYPT:' \
    -e 's:/var/spool/mail:/var/mail:'                   \
    -e '/PATH=/{s@/sbin:@@;s@/bin:@@}'                  \
    -i etc/login.defs

	touch /usr/bin/passwd
	./configure --sysconfdir=/etc   \
            --disable-static    \
            --with-{b,yes}crypt \
            --without-libbsd    \
            --with-group-name-max-length=32
	

	make
	make exec_prefix=/usr install
	make -C man install-man


	(Configure shadow )
	pwconv
	grpconv
	mkdir -p /etc/default
	useradd -D --gid 999

	sed -i '/MAIL/s/yes/no/' /etc/default/useradd
	passwd root
