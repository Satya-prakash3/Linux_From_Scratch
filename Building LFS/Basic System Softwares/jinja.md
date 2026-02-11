Jinja2 is a Python module that implements a simple pythonic template language.

1. Extraction

	tar -xvf jinja2-3.1.6.tar.gz
	cd jinja2-3.1.6

2. Building

	pip3 wheel -w dist --no-cache-dir --no-build-isolation --no-deps $PWD
	pip3 install --no-index --find-links dist Jinja2

