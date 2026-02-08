Wheel is a Python library that is the reference implementation of the Python wheel packaging standard.

1. Extraction

	tar -xvf wheel-0.46.1.tar.gz
	cd wheel-0.46.1

2. Building

	pip3 wheel -w dist --no-cache-dir --no-build-isolation --no-deps $PWD
	pip3 install --no-index --find-links dist wheel

