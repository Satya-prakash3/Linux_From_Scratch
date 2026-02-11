The Sysklogd package contains programs for logging system messages, such as those emitted by the kernel when unusual things happen.

1. Extraction

	tar -xvf sysklogd-2.7.2.tar.gz
	cd sysklogd-2.7.2

2. Building
	
	time { ./configure --prefix=/usr                  --sysconfdir=/etc              --runstatedir=/run             --without-logger               --disable-static               --docdir=/usr/share/doc/sysklogd-2.7.2 && make && make install; }
	

	cat > /etc/syslog.conf << "EOF"
# Begin /etc/syslog.conf

auth,authpriv.* -/var/log/auth.log
*.*;auth,authpriv.none -/var/log/sys.log
daemon.* -/var/log/daemon.log
kern.* -/var/log/kern.log
mail.* -/var/log/mail.log
user.* -/var/log/user.log
*.emerg *

# Do not open any internet ports.
secure_mode 2

# End /etc/syslog.conf
EOF
