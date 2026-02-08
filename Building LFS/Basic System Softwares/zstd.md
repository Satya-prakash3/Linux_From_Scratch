Zstandard is a real-time compression algorithm, providing high compression ratios. It offers a very wide range of compression / speed trade-offs, while being backed by a very fast decoder.

1. Extraction
	tar -xvf zstd-1.5.7.tar.gz
	cd zstd-1.5.7

2.  Building
	make prefix=/usr
	make check
	make prefix=/usr install

	rm -v /usr/lib/libzstd.a

