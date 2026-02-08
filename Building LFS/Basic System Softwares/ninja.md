Ninja is a small build system with a focus on speed.

1. Extraction

	tar -xvf ninja-1.13.1.tar.gz
	cd ninja-1.13.1

2. Building

	export NINJAJOBS=4
	sed -i '/int Guess/a \
  int   j = 0;\
  char* jobs = getenv( "NINJAJOBS" );\
  if ( jobs != NULL ) j = atoi( jobs );\
  if ( j > 0 ) return j;\
' src/ninja.cc

	python3 configure.py --bootstrap --verbose
	install -vm755 ninja /usr/bin/
	install -vDm644 misc/bash-completion /usr/share/bash-completion/completions/ninja
	install -vDm644 misc/zsh-completion  /usr/share/zsh/site-functions/_ninja

