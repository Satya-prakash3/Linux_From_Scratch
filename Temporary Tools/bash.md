The Bash package contains the Bourne-Again Shell.

1. Extraction

	tar -xvf bash-5.3.tar.gz
	cd bash-5.3

2. Building
	
	time { ./configure --prefix=/usr                                  --build=$(sh support/config.guess)             --host=$LFS_TGT                                --without-bash-malloc && make && make DESTDIR=$LFS install; }
	ln -sv bash $LFS/bin/sh

