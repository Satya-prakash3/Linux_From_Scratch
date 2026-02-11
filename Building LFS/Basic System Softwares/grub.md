The GRUB package contains the GRand Unified Bootloader.

1. Extraction

	tar -xvf grub-2.12.tar.xz
	cd grub-2.12

2. Building

	echo depends bli part_gpt > grub-core/extra_deps.lst
	./configure --prefix=/usr     \
            --sysconfdir=/etc \
            --disable-efiemu  \
            --disable-werror
	make
	make install

	mv -v /etc/bash_completion.d/grub /usr/share/bash-completion/completions

