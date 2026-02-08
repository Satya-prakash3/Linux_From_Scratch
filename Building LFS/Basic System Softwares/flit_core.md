Flit-core is the distribution-building parts of Flit (a packaging tool for simple Python modules).

1. Extraction

	tar -xvf flit_core-3.12.0.tar.gz
	cd flit_core-3.12.0

2. Building

	pip3 wheel -w dist --no-cache-dir --no-build-isolation --no-deps $PWD
	pip3 install --no-index --find-links dist flit_core
	
	
