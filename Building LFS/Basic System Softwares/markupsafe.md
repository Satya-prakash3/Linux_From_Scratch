MarkupSafe is a Python module that implements an XML/HTML/XHTML Markup safe string.

1. Extraction
	
	tar -xvf markupsafe-3.0.2.tar.gz
	cd markupsafe-3.0.2

2. Building

	pip3 wheel -w dist --no-cache-dir --no-build-isolation --no-deps $PWD
	pip3 install --no-index --find-links dist Markupsafe

