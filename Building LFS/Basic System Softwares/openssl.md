The OpenSSL package contains management tools and libraries relating to cryptography. These are useful for providing cryptographic functions to other packages, such as OpenSSH, email applications, and web browsers (for accessing HTTPS sites).

1. Extraction

	tar -xvf openssl-3.5.2.tar.gz
	cd openssl-3.5.2

2. Building

	./config --prefix=/usr         \
         --openssldir=/etc/ssl \
         --libdir=lib          \
         shared                \
         zlib-dynamic

	make
	HARNESS_JOBS=$(nproc) make test
	sed -i '/INSTALL_LIBS/s/libcrypto.a libssl.a//' Makefile
	make MANSUFFIX=ssl install
	
	mv -v /usr/share/doc/openssl /usr/share/doc/openssl-3.5.2
	cp -vfr doc/* /usr/share/doc/openssl-3.5.2


