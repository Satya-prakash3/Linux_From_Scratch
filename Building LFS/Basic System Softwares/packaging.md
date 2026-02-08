The packaging module is a Python library that provides utilities that implement the interoperability specifications which have clearly one correct behaviour (PEP440) or benefit greatly from having a single shared implementation (PEP425). This includes utilities for version handling, specifiers, markers, tags, and requirements.

1. Extraction

	tar -xvf packaging-25.0.tar.gz
	cd packaging-25.0

2. Building

	pip3 wheel -w dist --no-cache-dir --no-build-isolation --no-deps $PWD
	
