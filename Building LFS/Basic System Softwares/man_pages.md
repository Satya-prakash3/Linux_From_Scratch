The Man-pages package contains over 2,400 man pages.

1. Extraction
	tar -xvf man-pages-6.15.tar.xz
	cd man-pages-6.15

2. Building
	rm -v man3/crypt*
	time { make -R GIT=false prefix=/usr install; }


