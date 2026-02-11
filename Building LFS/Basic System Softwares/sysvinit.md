The SysVinit package contains programs for controlling the startup, running, and shutdown of the system.

1. Extraction

	tar -xvf sysvinit-3.14.tar.xz
	cd sysvinit-3.14

2. Building

	patch -Np1 -i ../sysvinit-3.14-consolidated-1.patch
	make
	make install
