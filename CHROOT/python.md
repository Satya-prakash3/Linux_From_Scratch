The Python 3 package contains the Python development environment. It is useful for object-oriented programming, writing scripts, prototyping large programs, and developing entire applications. Python is an interpreted computer language.

1. Extraction 
	tar -xvf Python-3.13.7.tar.xz
	cd Python-3.13.7

2.  Building
	time { ./configure --prefix=/usr                   --enable-shared                 --without-ensurepip             --without-static-libpython && make && make install; }

