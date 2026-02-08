The Xz package contains programs for compressing and decompressing files. It provides capabilities for the lzma and the newer xz compression formats. Compressing text files with xz yields a better compression percentage than with the traditional gzip or bzip2 commands.

1. Extraction
	time { ./configure --prefix=/usr                --disable-static             --docdir=/usr/share/doc/xz-5.8.1 && make && make check && make install; }

