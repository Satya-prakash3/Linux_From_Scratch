The Bash package contains the Bourne-Again Shell.

1. Extraction
	
	tar -xvf bash-5.3.tar.gz
	cd bash-5.3

2. Building

	time { ./configure --prefix=/usr                         --without-bash-malloc                 --with-installed-readline             --docdir=/usr/share/doc/bash-5.3 && make; }
	chown -R tester .
	LC_ALL=C.UTF-8 su -s /usr/bin/expect tester << "EOF"
set timeout -1
spawn make tests
expect eof
lassign [wait] _ _ _ value
exit $value
EOF
	
	make install
	exec /usr/bin/bash --login

