Setuptools is a tool used to download, build, install, upgrade, and uninstall Python packages.

1. Extraction

	tar -xvf setuptools-80.9.0.tar.gz
	cd setuptools-80.9.0

2. Building

	pip3 wheel -w dist --no-cache-dir --no-build-isolation --no-deps $PWD
	pip3 install --no-index --find-links dist setuptools

