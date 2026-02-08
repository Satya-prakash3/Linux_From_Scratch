The Diffutils package contains programs that show the differences between files or directories.

1. Extraction

	tar -xvf diffutils-3.12.tar.xz
	cd diffutils-3.12

2. Building

	time { ./configure --prefix=/usr               --host=$LFS_TGT             gl_cv_func_strcasecmp_works=y             --build=$(./build-aux/config.guess) && make && make DESTDIR=$LFS install; }

