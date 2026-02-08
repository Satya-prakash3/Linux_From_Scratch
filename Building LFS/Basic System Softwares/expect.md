The Expect package contains tools for automating, via scripted dialogues, interactive applications such as telnet, ftp, passwd, fsck, rlogin, and tip. Expect is also useful for testing these same applications as well as easing all sorts of tasks that are prohibitively difficult with anything else. The DejaGnu framework is written in Expect.

1. Extraction
	tar -xvf expect5.45.4.tar.gz
	cd expect5.45.4

2. Building
	python3 -c 'from pty import spawn; spawn(["echo", "ok"])'
	
	patch -Np1 -i ../expect-5.45.4-gcc15-1.patch
	
	time { ./configure --prefix=/usr                       --with-tcl=/usr/lib                 --enable-shared                     --disable-rpath                     --mandir=/usr/share/man             --with-tclinclude=/usr/include && make && make test && make install; }

	ln -svf expect5.45.4/libexpect5.45.4.so /usr/lib

