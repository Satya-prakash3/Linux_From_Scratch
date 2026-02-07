The Perl package contains the Practical Extraction and Report Language.

1. Extraction
	tar -xvf perl-5.42.0.tar.xz
	cd perl-5.42.0

2. Building
	time { sh Configure -des                                                      -D prefix=/usr                                            -D vendorprefix=/usr                                      -D useshrplib                                             -D privlib=/usr/lib/perl5/5.42/core_perl                  -D archlib=/usr/lib/perl5/5.42/core_perl                  -D sitelib=/usr/lib/perl5/5.42/site_perl                  -D sitearch=/usr/lib/perl5/5.42/site_perl                 -D vendorlib=/usr/lib/perl5/5.42/vendor_perl              -D vendorarch=/usr/lib/perl5/5.42/vendor_perl && make && make install; }
