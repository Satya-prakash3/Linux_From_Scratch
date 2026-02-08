The Acl package contains utilities to administer Access Control Lists, which are used to define fine-grained discretionary access rights for files and directories.

1. Etraction
	
	tar -xvf acl-2.3.2.tar.xz
	cd acl-2.3.2

2. Buildling
	
	time { ./configure --prefix=/usr                --disable-static             --docdir=/usr/share/doc/acl-2.3.2 && make; }

	make check
	make install
	
