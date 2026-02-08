The Libcap package implements the userspace interface to the POSIX 1003.1e capabilities available in Linux kernels. These capabilities partition the all-powerful root privilege into a set of distinct privileges.

1. Extraction 
	
	tar -xvf libcap-2.76.tar.xz
	cd libcap-2.76

2. Building
	sed -i '/install -m.*STA/d' libcap/Makefile

	make prefix=/usr lib=lib
	make test
	make prefix=/usr lib=lib install

