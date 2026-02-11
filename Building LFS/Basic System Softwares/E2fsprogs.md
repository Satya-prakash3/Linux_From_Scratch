The E2fsprogs package contains the utilities for handling the ext2 file system. It also supports the ext3 and ext4 journaling file systems.

1. Extraction

	tar -xvf e2fsprogs-1.47.3.tar.gz
	cd e2fsprogs-1.47.3

2. Building
	
	mkdir -v build
	cd build

	time { ../configure --prefix=/usr                    --sysconfdir=/etc                --enable-elf-shlibs              --disable-libblkid               --disable-libuuid                --disable-uuidd                  --disable-fsck && make; }

	make check
	make install

	rm -fv /usr/lib/{libcom_err,libe2p,libext2fs,libss}.a
	gunzip -v /usr/share/info/libext2fs.info.gz
	install-info --dir-file=/usr/share/info/dir /usr/share/info/libext2fs.info
	
	makeinfo -o      doc/com_err.info ../lib/et/com_err.texinfo
	install -v -m644 doc/com_err.info /usr/share/info
	install-info --dir-file=/usr/share/info/dir /usr/share/info/com_err.info
	sed 's/metadata_csum_seed,//' -i /etc/mke2fs.conf

