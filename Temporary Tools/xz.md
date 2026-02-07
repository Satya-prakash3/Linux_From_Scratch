The Xz package contains programs for compressing and decompressing files. It provides capabilities for the lzma and the newer xz compression formats. Compressing text files with xz yields a better compression percentage than with the traditional gzip or bzip2 commands.

1. Extraction
	tar -xvf xz-5.8.1.tar.xz
	cd xz-5.8.1

2. building
	time { ./configure --prefix=/usr                                 --host=$LFS_TGT                               --build=$(build-aux/config.guess)             --disable-static                              --docdir=/usr/share/doc/xz-5.8.1 && make && make DESTDIR=$LFS install; }
	rm -v $LFS/usr/lib/liblzma.la

