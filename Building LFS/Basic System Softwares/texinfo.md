The Texinfo package contains programs for reading, writing, and converting info pages.

1. Extraction

	tar -xvf texinfo-7.2.tar.xz
	cd texinfo-7.2

2. Building

	sed 's/! $output_file eq/$output_file ne/' -i tp/Texinfo/Convert/*.pm
	time { ./configure --prefix=/usr && make && make check && make install; }
	
	make TEXMF=/usr/share/texmf install-tex

	pushd /usr/share/info
  rm -v dir
  for f in *
    do install-info $f dir 2>/dev/null
  done
popd
