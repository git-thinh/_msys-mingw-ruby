# MinGW-w64:
	-> Set PATH = MinGW-w64/bin;...
	mingw-w64-install.exe or mingw-get-setup.exe: 
	mingw-w64-x86_64-7.2.0-win32-sjlj-rt_v5-rev1 or mingw-w64-x86_64-7.2.0-posix-seh-rt_v5-rev1
	https://sourceforge.net/projects/mingw-w64/files/Toolchains%20targetting%20Win32/Personal%20Builds/mingw-builds/installer/
	https://sourceforge.net/projects/mingw/files/
	https://sourceforge.net/projects/mingw/files/latest/download?source=files
	
	
# MSYS: 

	Minimal SYStem is a minimal POSIX system used in the Win32 OS to accomplish configuration and making of packages. MSYS is a fork of Cygwin and is more friendly to the Win32 user.  It offers only a user land environment for MinGW development.  It converts posix paths before executing a "native" win32 program.  This allows the users of the MinGW version of GCC to port and build packages in a GNU familiar way and removes the UNIX complexities that Cygwin adds.	
	-> Set PATH = C:\msys\1.0\bin;...
	MSYS-1.0.11.exe
	http://www.mingw.org/wiki/MSYS
	https://sourceforge.net/projects/mingw/files/MSYS/Base/msys-core/msys-1.0.11/
	https://sourceforge.net/projects/mingw/files/MSYS/Base/msys-core/msys-1.0.11/MSYS-1.0.11.exe/download
	http://ftp.ntua.gr/mirror/mingw/MSYS/Base/msys-core/msys-1.0.11/MSYS-1.0.11.exe
	

# MSYS2: 
	-> Set PATH = ../bin;...
	https://github.com/msys2/msys2/wiki
	MSYS2 is a software distro and building platform for Windows
	At its core is an independent rewrite of MSYS, based on modern Cygwin (POSIX compatibility layer) and MinGW-w64 with the aim of better interoperability with native Windows software. It provides a bash shell, Autotools, revision control systems and the like for building native Windows applications using MinGW-w64 toolchains.

	msys2-x86_64-20161025.exe
	http://www.msys2.org/
	http://repo.msys2.org/distrib/x86_64/msys2-x86_64-20161025.exe

	- Tick Run MSYS2 now  
	- Update the package database and core system packages with: 
		$ pacman -Syu
		$ pacman -Syu
		$ pacman -Syu
		
	- If needed, close MSYS2, run it again from Start menu. Update the rest with:
		pacman -Su
		
	- Install and update packges for developer: git, cmake, ...
		$ pacman -S git
		$ pacman -S cmake
		$ pacman -S make	
		 
		$ cmake --version
		$ g++ --version
		
# RubyInstaller2:
	-> Set PATH = ../bin;...
	rubyinstaller-2.5.0-1-x64.exe
	https://github.com/oneclick/rubyinstaller2-packages
	For instance these popular gems can be installed like so from the source gem:
	To install sqlite3 gem:
		> ridk exec pacman -S mingw-w64-x86_64-sqlite3
		> gem install sqlite3 --platform ruby
	To install nokogiri gem:
		> ridk exec pacman -S mingw-w64-x86_64-libxslt
		> gem install nokogiri --platform ruby -- --use-system-libraries
	
# MSYS2-packages: 

	$ git clone https://github.com/Alexpux/MSYS2-packages.git
	To build these, run msys2_shell.cmd then from the bash prompt.
			$ cd ${package-name}
			$ makepkg
			
	To install the built package(s).
			$ pacman -U ${package-name}*.pkg.tar.xz
			
	If you don't have the group base-devel installed, please install.
			$ pacman -S base-devel

# MINGW-packages: 

	$ git clone https://github.com/Alexpux/MINGW-packages.git
	Install the pre-built binary package: 
			$ pacman -S ${package-name}
			
	you can build any package using the following command:
			$ cd ${package-name}
			$ MINGW_INSTALLS=mingw64 makepkg-mingw -sLf
			
	After that you can install the freshly built package(s) with the following command:
			$ pacman -U ${package-name}*.pkg.tar.xz
			
			
------------------------------------------------------------------------
# Downloading & Building Git, MingW-w64: CMake, Make(MSYS/1.0/bin):
Boost:
	- Download && unzip https://dl.bintray.com/boostorg/release/1.66.0/source/boost_1_66_0.zip
	> cd boost_1_66_0
	> bootstrap.bat mingw  // for 32bit
	> b2 toolset=gcc variant=release link=static --with-system --with-filesystem
GRPC:
	> git submodule init
	> git submodule update

SFML:
	> cd \
	> cd && git clone https://github.com/SFML/SFML.git
	> cmake -G "MinGW Makefiles" -DCMAKE_BUILD_TYPE=RELEASE -DBUILD_SHARED_LIBS=0 ../
	> mingw32-make install
	
More tutorial:
	https://github.com/cpluspluscom/ChessPlusPlus/wiki/Building
	https://github.com/cpluspluscom/ChessPlusPlus/wiki/MinGW-Build-Tutorial
	
------------------------------------------------------------------------
@MSYS2-packages:
	apr-util
	apr
	asciidoc
	aspell-en
	aspell
	atool
	autoconf-archive
	autoconf
	autoconf2.13
	autogen
	automake-wrapper
	automake1.10
	automake1.11
	automake1.12
	automake1.13
	automake1.14
	automake1.15
	automake1.6
	automake1.7
	automake1.8
	automake1.9
	axel
	bash-completion
	bash
	bc
	binutils
	bison
	bisoncpp
	busybox
	bzip2
	bzr-fastimport
	bzr
	c-ares
	ca-certificates
	catgets
	ccache
	cdecl
	cgdb
	clang-svn
	cloc
	cloog
	cmake
	cocom
	colordiff
	colormake-git
	coreutils
	crosstool-ng-git
	crosstool-ng
	cscope
	ctags
	curl
	cvs
	cygrunsrv
	cyrus-sasl
	dash
	db
	dejagnu
	delta
	depot-tools-git
	dialog
	diffstat
	diffutils
	docbook-dsssl
	docbook-mathml
	docbook-sgml
	docbook-sgml31
	docbook-xml
	docbook-xsl
	docx2txt
	dos2unix
	doxygen
	dtc
	dwz
	easyoptions-git
	ed
	elfutils
	elinks-git
	emacs
	expat
	expect
	fcode-utils
	file
	filesystem
	findutils
	fish
	flex
	flexcpp
	fzy
	gamin
	gawk
	gc
	gcc
	gdb
	gdbm
	gengetopt
	getent
	getopt
	gettext
	git-bzr-ng-git
	git-extras-git
	git-flow
	git
	glib2
	global
	gmp
	gnome-common
	gnome-doc-utils
	gnu-netcat
	gnupg
	gnutls
	gperf
	gpgme
	gradle
	grep
	grml-zsh-config
	groff
	gtk-doc
	guile
	gyp-git
	gzip
	heimdal
	help2man
	icmake
	icon-naming-utils
	icu
	idutils
	inetutils
	intltool
	irssi-git
	irssi
	isl
	itstool
	jansson
	jhbuild-git
	jsoncpp
	lemon
	less
	lftp
	libarchive
	libargp
	libassuan
	libbobcat
	libcrypt
	libedit
	libelf
	libevent
	libffi-git
	libffi
	libgcrypt
	libgpg-error
	libiconv
	libidn
	libidn2
	libksba
	libmetalink
	libnghttp2
	libpipeline
	libpsl
	libqrencode-git
	libssh2
	libtasn1
	libtirpc
	libtool
	libtre-git
	libunistring
	libuv
	libxml2
	libxslt
	lndir
	lzip
	lzo2
	m4
	make-git
	make
	man-db
	man-pages-posix
	man
	markdown
	mc
	mercurial
	midipix-cross-binutils
	midipix-cross-gcc-git
	midipix-cross-musl
	midipix-cross-psxstub
	mingw-w64-cross-binutils-git
	mingw-w64-cross-binutils
	mingw-w64-cross-conemu-git
	mingw-w64-cross-crt-git
	mingw-w64-cross-gcc-git
	mingw-w64-cross-gcc
	mingw-w64-cross-headers-git
	mingw-w64-cross-tools-git
	mingw-w64-cross-windows-default-manifest
	mingw-w64-cross-winpthreads-git
	mingw-w64-cross-winstorecompat-git
	mingw-w64-cross-zlib
	mintty-git
	mintty
	mksh
	moreutils
	mosh
	mpc
	mpdecimal
	mpfr
	msys2-keyring
	msys2-launcher-git
	msys2-runtime
	msys2-unlocker
	msys2-w32api-headers
	msys2-w32api-runtime
	mutt
	nano-syntax-highlighting-git
	nano
	nasm
	ncurses
	neon
	nettle
	npth
	openbios
	openbsd-netcat
	openssh
	openssl
	p11-kit
	p7zip
	pacman-mirrors
	pacman
	pactoys-git
	parallel
	pass
	patch
	patchutils
	pax-git
	pcre
	perl-Algorithm-Diff
	perl-Archive-Zip
	perl-Authen-SASL
	perl-Benchmark-Timer
	perl-Capture-Tiny
	perl-Carp-Clan
	perl-Compress-Bzip2
	perl-Convert-BinHex
	perl-Crypt-SSLeay
	perl-DBI
	perl-Date-Calc
	perl-Digest-HMAC
	perl-Digest-MD4
	perl-Encode-Locale
	perl-Encode-compat
	perl-Error
	perl-Exporter-Lite
	perl-Exporter-Tiny
	perl-ExtUtils-Depends
	perl-ExtUtils-MakeMaker
	perl-ExtUtils-PkgConfig
	perl-File-Copy-Recursive
	perl-File-Listing
	perl-File-Next
	perl-File-Which
	perl-Font-TTF
	perl-Getopt-Tabular
	perl-HTML-Parser
	perl-HTML-Tagset
	perl-HTTP-Cookies
	perl-HTTP-Daemon
	perl-HTTP-Date
	perl-HTTP-Message
	perl-HTTP-Negotiate
	perl-IO-HTML
	perl-IO-Socket-INET6
	perl-IO-Socket-SSL
	perl-IO-String
	perl-IO-stringy
	perl-IPC-Run3
	perl-LWP-MediaTypes
	perl-LWP-Protocol-https
	perl-List-MoreUtils
	perl-Locale-Gettext
	perl-MIME-Charset
	perl-MIME-tools
	perl-MailTools
	perl-Math-Int64
	perl-Module-Build
	perl-Mozilla-CA
	perl-Net-DNS
	perl-Net-HTTP
	perl-Net-IP
	perl-Net-SMTP-SSL
	perl-Net-SSLeay
	perl-Path-Class
	perl-Probe-Perl
	perl-Regexp-Common
	perl-Socket6
	perl-Sort-Versions
	perl-Sys-CPU
	perl-TAP-Harness-Archive
	perl-TermReadKey
	perl-Test-Harness
	perl-Test-Pod
	perl-Test-Script
	perl-Text-CharWidth
	perl-Text-WrapI18N
	perl-TimeDate
	perl-Try-Tiny
	perl-URI
	perl-Unicode-GCString
	perl-WWW-RobotRules
	perl-XML-LibXML
	perl-XML-NamespaceSupport
	perl-XML-Parser
	perl-XML-SAX-Base
	perl-XML-SAX
	perl-XML-Simple
	perl-YAML-Syck
	perl-YAML-Tiny
	perl-YAML
	perl-ack
	perl-common-sense
	perl-libwww
	perl-sgmls
	perl
	pinentry
	pkg-config
	pkgconf
	pkgfile
	po4a
	procps-ng
	procps
	protobuf
	psmisc
	pth
	publicsuffix-list
	pv
	pwgen
	python-appdirs
	python-beaker
	python-colorama
	python-distutils-extra
	python-mako
	python-markupsafe
	python-mock
	python-nose
	python-packaging
	python-pip
	python-py
	python-pyalpm
	python-pygments
	python-pyparsing
	python-pytest
	python-setuptools-scm
	python-setuptools
	python-six
	python2-fastimport
	python2
	python3
	quilt
	rarian
	rcs
	re2c
	readline
	rebase
	remake-git
	rhash
	rsync
	rsync2
	ruby
	scons
	screenfetch
	sed
	serf
	setconf
	sgml-common
	sharutils
	socat
	sqlite
	ssh-pageant-git
	sshpass
	subversion
	swig
	tar
	task
	tcl
	tcsh
	termbox
	texinfo
	tftp-hpa
	tig
	time
	tio
	tmux
	tree
	ttyrec
	txt2tags
	tzcode
	ucl
	unrar
	unzip
	upx
	util-linux
	util-macros
	vim
	vimpager-git
	vimpager
	w3m
	wcd
	wget
	which
	whois
	windows-default-manifest
	winln
	winpty-git
	winpty
	xdelta3
	xmlto
	xorriso
	xproto
	xz-git
	xz
	yaml
	yasm
	yelp-tools
	yelp-xsl
	yodl
	zip
	zlib
	znc-git
	zsh
@MINGW-packages:	
	mingw-w64-3proxy
	mingw-w64-4th
	mingw-w64-MinHook
	mingw-w64-OpenBLAS-git
	mingw-w64-OpenSceneGraph-git
	mingw-w64-OpenSceneGraph
	mingw-w64-PKGBUILD-common
	mingw-w64-PKGBUILD-templates
	mingw-w64-SDL
	mingw-w64-SDL2
	mingw-w64-SDL2_gfx
	mingw-w64-SDL2_image
	mingw-w64-SDL2_mixer
	mingw-w64-SDL2_net
	mingw-w64-SDL2_sound-hg
	mingw-w64-SDL2_ttf
	mingw-w64-SDL_gfx
	mingw-w64-SDL_image
	mingw-w64-SDL_mixer
	mingw-w64-SDL_net
	mingw-w64-SDL_ttf
	mingw-w64-a52dec
	mingw-w64-adns
	mingw-w64-adwaita-icon-theme
	mingw-w64-ag
	mingw-w64-alembic
	mingw-w64-allegro
	mingw-w64-alure
	mingw-w64-angleproject-git
	mingw-w64-ansicon-git
	mingw-w64-antiword
	mingw-w64-antlr3
	mingw-w64-antlr4-runtime-cpp
	mingw-w64-apr-util
	mingw-w64-apr
	mingw-w64-argon2
	mingw-w64-aria2
	mingw-w64-aribb24
	mingw-w64-arm-none-eabi-binutils
	mingw-w64-arm-none-eabi-gcc
	mingw-w64-arm-none-eabi-gdb
	mingw-w64-arm-none-eabi-newlib
	mingw-w64-armadillo
	mingw-w64-arpack
	mingw-w64-asciidoctor
	mingw-w64-aspell-de
	mingw-w64-aspell-en
	mingw-w64-aspell-es
	mingw-w64-aspell-fr
	mingw-w64-aspell-ru
	mingw-w64-aspell
	mingw-w64-assimp-git
	mingw-w64-assimp
	mingw-w64-astyle
	mingw-w64-atk
	mingw-w64-atkmm
	mingw-w64-atom-editor-git
	mingw-w64-atom-shell-git
	mingw-w64-attica-qt5
	mingw-w64-avrdude
	mingw-w64-aztecgen
	mingw-w64-babl
	mingw-w64-badvpn
	mingw-w64-bc
	mingw-w64-binaryen
	mingw-w64-binutils-git
	mingw-w64-binutils
	mingw-w64-bison
	mingw-w64-blender-git
	mingw-w64-blender
	mingw-w64-boost
	mingw-w64-box2d
	mingw-w64-breakpad-git
	mingw-w64-bsdfprocessor
	mingw-w64-btyacc
	mingw-w64-bullet
	mingw-w64-bwidget
	mingw-w64-bzip2
	mingw-w64-c-ares
	mingw-w64-c99-to-c89-git
	mingw-w64-ca-certificates
	mingw-w64-cairo
	mingw-w64-cairomm
	mingw-w64-capstone
	mingw-w64-catch
	mingw-w64-ccache
	mingw-w64-cccl
	mingw-w64-cego
	mingw-w64-cegui
	mingw-w64-celt
	mingw-w64-cereal
	mingw-w64-ceres-solver
	mingw-w64-cfitsio
	mingw-w64-cgal
	mingw-w64-check
	mingw-w64-chipmunk
	mingw-w64-chromaprint
	mingw-w64-chromium-dev
	mingw-w64-clang-svn
	mingw-w64-clang
	mingw-w64-clang35
	mingw-w64-cling-git
	mingw-w64-clink-git
	mingw-w64-cloog
	mingw-w64-clucene
	mingw-w64-clutter-gst
	mingw-w64-clutter-gtk
	mingw-w64-clutter
	mingw-w64-cmake-doc-qt
	mingw-w64-cmake-git
	mingw-w64-cmake
	mingw-w64-cmark
	mingw-w64-cmocka
	mingw-w64-cocos2d-x-console-git
	mingw-w64-cocos2d-x-git
	mingw-w64-cocos2d-x
	mingw-w64-codelite-git
	mingw-w64-cogl
	mingw-w64-coin3d-hg
	mingw-w64-collada-dom-svn
	mingw-w64-conemu-git
	mingw-w64-confuse
	mingw-w64-connect
	mingw-w64-coq
	mingw-w64-cotire
	mingw-w64-cppcheck
	mingw-w64-cppreference-qt
	mingw-w64-cpptest
	mingw-w64-cppunit
	mingw-w64-creduce-git
	mingw-w64-creduce
	mingw-w64-crt-git
	mingw-w64-crypto++-git
	mingw-w64-crypto++
	mingw-w64-csfml
	mingw-w64-ctags
	mingw-w64-ctpl-git
	mingw-w64-cunit
	mingw-w64-curl
	mingw-w64-cyrus-sasl
	mingw-w64-cython-git
	mingw-w64-cython
	mingw-w64-d-feet
	mingw-w64-daala-git
	mingw-w64-darktable
	mingw-w64-db
	mingw-w64-dbus-glib
	mingw-w64-dbus
	mingw-w64-dcadec
	mingw-w64-desktop-file-utils
	mingw-w64-devcon-git
	mingw-w64-devhelp
	mingw-w64-devil
	mingw-w64-diffutils
	mingw-w64-dime-hg
	mingw-w64-discount
	mingw-w64-distorm
	mingw-w64-djvulibre
	mingw-w64-dlfcn-git
	mingw-w64-dlfcn
	mingw-w64-dlib
	mingw-w64-dmake
	mingw-w64-dnscrypt-proxy
	mingw-w64-dnssec-anchors
	mingw-w64-docbook-dsssl
	mingw-w64-docbook-mathml
	mingw-w64-docbook-sgml
	mingw-w64-docbook-sgml31
	mingw-w64-docbook-xml
	mingw-w64-docbook-xsl
	mingw-w64-doxygen
	mingw-w64-dragon
	mingw-w64-drmingw-git
	mingw-w64-drmingw
	mingw-w64-dsdp
	mingw-w64-ducible-git
	mingw-w64-dumb
	mingw-w64-edd-dbg
	mingw-w64-edd-fungo
	mingw-w64-editrights
	mingw-w64-eigen3
	mingw-w64-emacs-git
	mingw-w64-emacs
	mingw-w64-enca
	mingw-w64-enchant
	mingw-w64-enet
	mingw-w64-eog-plugins
	mingw-w64-eog
	mingw-w64-evince
	mingw-w64-exiv2
	mingw-w64-expat
	mingw-w64-extra-cmake-modules
	mingw-w64-faac
	mingw-w64-faad2
	mingw-w64-fann
	mingw-w64-farstream
	mingw-w64-fastjar
	mingw-w64-fdk-aac
	mingw-w64-ffmpeg
	mingw-w64-ffms2
	mingw-w64-fftw
	mingw-w64-field3d
	mingw-w64-file
	mingw-w64-firebird-git
	mingw-w64-firebird2-git
	mingw-w64-firefox
	mingw-w64-flac
	mingw-w64-flatbuffers
	mingw-w64-flex
	mingw-w64-flexdll
	mingw-w64-flickcurl
	mingw-w64-fltk
	mingw-w64-fluidsynth
	mingw-w64-fmt
	mingw-w64-fontconfig
	mingw-w64-fossil-fossil
	mingw-w64-fossil
	mingw-w64-fox
	mingw-w64-freeglut
	mingw-w64-freeimage
	mingw-w64-freerdp-git
	mingw-w64-freetds
	mingw-w64-freetype
	mingw-w64-fribidi
	mingw-w64-ftgl
	mingw-w64-gavl
	mingw-w64-gc
	mingw-w64-gcc-git
	mingw-w64-gcc
	mingw-w64-gd
	mingw-w64-gdal
	mingw-w64-gdb-git
	mingw-w64-gdb
	mingw-w64-gdbm
	mingw-w64-gdcm
	mingw-w64-gdk-pixbuf2
	mingw-w64-gdl
	mingw-w64-gdl2
	mingw-w64-gdlmm2
	mingw-w64-geany-plugins
	mingw-w64-geany
	mingw-w64-gedit-plugins
	mingw-w64-gedit
	mingw-w64-gegl
	mingw-w64-geoclue
	mingw-w64-geocode-glib
	mingw-w64-geoip
	mingw-w64-geoip2-database
	mingw-w64-geos
	mingw-w64-gettext
	mingw-w64-gexiv2
	mingw-w64-gflags
	mingw-w64-ghc
	mingw-w64-ghex
	mingw-w64-ghostscript
	mingw-w64-giflib
	mingw-w64-gimp-ufraw
	mingw-w64-gimp
	mingw-w64-git-git
	mingw-w64-git-lfs
	mingw-w64-git-repo
	mingw-w64-git
	mingw-w64-gitg
	mingw-w64-gl2ps
	mingw-w64-glade
	mingw-w64-glade3
	mingw-w64-glbinding
	mingw-w64-glew
	mingw-w64-glfw
	mingw-w64-glib-networking
	mingw-w64-glib2-git
	mingw-w64-glib2
	mingw-w64-glibmm
	mingw-w64-glm
	mingw-w64-global
	mingw-w64-globjects
	mingw-w64-glog
	mingw-w64-glpk
	mingw-w64-glsl-optimizer-git
	mingw-w64-glslang
	mingw-w64-gmime
	mingw-w64-gmp
	mingw-w64-gnome-calculator
	mingw-w64-gnome-common
	mingw-w64-gnome-doc-utils
	mingw-w64-gnome-js-common
	mingw-w64-gnu-cobol-svn
	mingw-w64-gnucobol
	mingw-w64-gnupg
	mingw-w64-gnuplot
	mingw-w64-gnutls
	mingw-w64-go
	mingw-w64-gobject-introspection
	mingw-w64-goocanvas
	mingw-w64-googletest-git
	mingw-w64-gperf
	mingw-w64-gpgme
	mingw-w64-gphoto2
	mingw-w64-gplugin
	mingw-w64-gprbuild-bootstrap-git
	mingw-w64-gprbuild-gpl
	mingw-w64-graphene
	mingw-w64-graphicsmagick
	mingw-w64-graphite2
	mingw-w64-graphviz
	mingw-w64-grep
	mingw-w64-grpc
	mingw-w64-gsasl
	mingw-w64-gsettings-desktop-schemas
	mingw-w64-gsl
	mingw-w64-gsm
	mingw-w64-gspell
	mingw-w64-gss
	mingw-w64-gst-editing-services-git
	mingw-w64-gst-editing-services
	mingw-w64-gst-libav-git
	mingw-w64-gst-libav
	mingw-w64-gst-plugins-bad-git
	mingw-w64-gst-plugins-bad
	mingw-w64-gst-plugins-base-git
	mingw-w64-gst-plugins-base
	mingw-w64-gst-plugins-good-git
	mingw-w64-gst-plugins-good
	mingw-w64-gst-plugins-ugly-git
	mingw-w64-gst-plugins-ugly
	mingw-w64-gst-python-git
	mingw-w64-gst-python
	mingw-w64-gst-rtsp-server-git
	mingw-w64-gst-rtsp-server
	mingw-w64-gstreamer-git
	mingw-w64-gstreamer
	mingw-w64-gtef
	mingw-w64-gtest
	mingw-w64-gtk-doc
	mingw-w64-gtk-engine-murrine
	mingw-w64-gtk-engines
	mingw-w64-gtk-vnc
	mingw-w64-gtk2
	mingw-w64-gtk3-git
	mingw-w64-gtk3
	mingw-w64-gtkada
	mingw-w64-gtkglext
	mingw-w64-gtkhtml3
	mingw-w64-gtkimageview
	mingw-w64-gtkmm
	mingw-w64-gtkmm3
	mingw-w64-gtksourceview2
	mingw-w64-gtksourceview3
	mingw-w64-gtksourceviewmm2
	mingw-w64-gtksourceviewmm3
	mingw-w64-gtkspell
	mingw-w64-gtkspell3
	mingw-w64-gtkwave
	mingw-w64-guile
	mingw-w64-gxml
	mingw-w64-h2o
	mingw-w64-harfbuzz
	mingw-w64-hclient
	mingw-w64-hdf5
	mingw-w64-headers-git
	mingw-w64-hicolor-icon-theme
	mingw-w64-hidapi
	mingw-w64-hlsl2glsl-git
	mingw-w64-http-parser
	mingw-w64-hub
	mingw-w64-hunspell-en
	mingw-w64-hunspell
	mingw-w64-hyphen
	mingw-w64-icon-naming-utils
	mingw-w64-icoutils
	mingw-w64-icu
	mingw-w64-id3lib
	mingw-w64-ilmbase
	mingw-w64-imagemagick
	mingw-w64-indent
	mingw-w64-inkscape
	mingw-w64-innoextract
	mingw-w64-insight
	mingw-w64-intel-tbb
	mingw-w64-irrlicht
	mingw-w64-isl
	mingw-w64-iso-codes
	mingw-w64-itk
	mingw-w64-jansson
	mingw-w64-jasper
	mingw-w64-jbigkit
	mingw-w64-jemalloc
	mingw-w64-jpegoptim
	mingw-w64-jq
	mingw-w64-json-c
	mingw-w64-json-glib
	mingw-w64-jsoncpp
	mingw-w64-jsonrpc-glib
	mingw-w64-jucipp-git
	mingw-w64-jxrlib
	mingw-w64-kactivities-qt5
	mingw-w64-karchive-qt5
	mingw-w64-kauth-qt5
	mingw-w64-kcodecs-qt5
	mingw-w64-kcompletion-qt5
	mingw-w64-kconfig-qt5
	mingw-w64-kconfigwidgets-qt5
	mingw-w64-kcoreaddons-qt5
	mingw-w64-kcrash-qt5
	mingw-w64-kcwsh-qt5-git
	mingw-w64-kdbusaddons-qt5
	mingw-w64-kdoctools-qt5
	mingw-w64-kfilemetadata-qt5
	mingw-w64-kglobalaccel-qt5
	mingw-w64-kguiaddons-qt5
	mingw-w64-ki18n-qt5
	mingw-w64-kicad-doc
	mingw-w64-kicad-git
	mingw-w64-kiconthemes-qt5
	mingw-w64-kidletime-qt5
	mingw-w64-kimageformats-qt5
	mingw-w64-kiss_fft
	mingw-w64-kitemmodels-qt5
	mingw-w64-kitemviews-qt5
	mingw-w64-kjobwidgets-qt5
	mingw-w64-kjs-qt5
	mingw-w64-kpackage-qt5
	mingw-w64-kplotting-qt5
	mingw-w64-kqoauth-qt4
	mingw-w64-krita-git
	mingw-w64-kservice-qt5
	mingw-w64-ktextwidgets-qt5
	mingw-w64-kunitconversion-qt5
	mingw-w64-kvazaar
	mingw-w64-kwidgetsaddons-qt5
	mingw-w64-kwindowsystem-qt5
	mingw-w64-kxmlgui-qt5
	mingw-w64-l-smash
	mingw-w64-ladspa-sdk
	mingw-w64-lame
	mingw-w64-lapack
	mingw-w64-lasem
	mingw-w64-laszip
	mingw-w64-latexila
	mingw-w64-lcms
	mingw-w64-lcms2
	mingw-w64-lcov
	mingw-w64-ldns
	mingw-w64-leechcraft-git
	mingw-w64-lensfun
	mingw-w64-leptonica
	mingw-w64-lfcbase
	mingw-w64-lfcxml
	mingw-w64-libao
	mingw-w64-libarchive
	mingw-w64-libart_lgpl
	mingw-w64-libass
	mingw-w64-libassuan
	mingw-w64-libatomic_ops
	mingw-w64-libblocksruntime
	mingw-w64-libbluray
	mingw-w64-libbotan
	mingw-w64-libbs2b
	mingw-w64-libbsdf
	mingw-w64-libc++
	mingw-w64-libc++abi
	mingw-w64-libcaca
	mingw-w64-libcddb
	mingw-w64-libcdio-paranoia
	mingw-w64-libcdio
	mingw-w64-libcdr
	mingw-w64-libcello-git
	mingw-w64-libcerf
	mingw-w64-libchamplain
	mingw-w64-libcmis
	mingw-w64-libconfig
	mingw-w64-libcroco
	mingw-w64-libcue
	mingw-w64-libdca-git
	mingw-w64-libdvbpsi
	mingw-w64-libdvdcss
	mingw-w64-libdvdnav
	mingw-w64-libdvdread
	mingw-w64-libebml
	mingw-w64-libelf
	mingw-w64-libepoxy
	mingw-w64-libevent
	mingw-w64-libexif
	mingw-w64-libffi
	mingw-w64-libfilezilla
	mingw-w64-libfreexl
	mingw-w64-libftdi
	mingw-w64-libgadu
	mingw-w64-libgcrypt
	mingw-w64-libgd
	mingw-w64-libgda
	mingw-w64-libgdata
	mingw-w64-libgdiplus
	mingw-w64-libgee
	mingw-w64-libgeotiff
	mingw-w64-libgit2-glib
	mingw-w64-libgit2
	mingw-w64-libglade
	mingw-w64-libgme
	mingw-w64-libgnomecanvas
	mingw-w64-libgnurx
	mingw-w64-libgoom2
	mingw-w64-libgpg-error
	mingw-w64-libgphoto2
	mingw-w64-libgsf
	mingw-w64-libguess
	mingw-w64-libgusb
	mingw-w64-libgweather
	mingw-w64-libgxps
	mingw-w64-libharu
	mingw-w64-libical-glib
	mingw-w64-libical
	mingw-w64-libiconv
	mingw-w64-libid3tag
	mingw-w64-libidl2
	mingw-w64-libidn
	mingw-w64-libidn2
	mingw-w64-libilbc
	mingw-w64-libimagequant
	mingw-w64-libimobiledevice
	mingw-w64-libjpeg-turbo
	mingw-w64-libkcw-qt5-git
	mingw-w64-libkml
	mingw-w64-libksba
	mingw-w64-liblas
	mingw-w64-liblastfm-qt4
	mingw-w64-liblastfm
	mingw-w64-liblqr
	mingw-w64-libmad
	mingw-w64-libmangle-git
	mingw-w64-libmariadbclient
	mingw-w64-libmatroska
	mingw-w64-libmaxminddb
	mingw-w64-libmetalink
	mingw-w64-libmfx
	mingw-w64-libmicrohttpd
	mingw-w64-libmicroutils
	mingw-w64-libmikmod
	mingw-w64-libmimic
	mingw-w64-libmng
	mingw-w64-libmodbus-git
	mingw-w64-libmodplug
	mingw-w64-libmongoose-git
	mingw-w64-libmongoose
	mingw-w64-libmowgli
	mingw-w64-libmpcdec
	mingw-w64-libmpeg2-git
	mingw-w64-libmypaint-git
	mingw-w64-libmypaint
	mingw-w64-libnice
	mingw-w64-libnotify
	mingw-w64-libntlm
	mingw-w64-liboauth
	mingw-w64-libodfgen
	mingw-w64-libogg
	mingw-w64-libosmpbf-git
	mingw-w64-libotr
	mingw-w64-libpaper
	mingw-w64-libpeas
	mingw-w64-libplist
	mingw-w64-libpng
	mingw-w64-libproxy
	mingw-w64-libraqm
	mingw-w64-libraw
	mingw-w64-librescl
	mingw-w64-libressl
	mingw-w64-librest
	mingw-w64-librevenge
	mingw-w64-librocket-git
	mingw-w64-librsvg
	mingw-w64-librsync
	mingw-w64-libsamplerate
	mingw-w64-libsass
	mingw-w64-libsecret
	mingw-w64-libshout
	mingw-w64-libsigc++
	mingw-w64-libsignal-protocol-c-git
	mingw-w64-libsigsegv-git
	mingw-w64-libsigsegv
	mingw-w64-libsmallchange-hg
	mingw-w64-libsndfile
	mingw-w64-libsodium
	mingw-w64-libsoup
	mingw-w64-libsoxr
	mingw-w64-libspatialite
	mingw-w64-libspectre
	mingw-w64-libspiro
	mingw-w64-libsquish
	mingw-w64-libsrtp
	mingw-w64-libssh
	mingw-w64-libssh2
	mingw-w64-libswift
	mingw-w64-libsystre
	mingw-w64-libtasn1
	mingw-w64-libtheora
	mingw-w64-libtiff
	mingw-w64-libtommath
	mingw-w64-libtool
	mingw-w64-libtorrent-rasterbar
	mingw-w64-libtre-git
	mingw-w64-libunistring
	mingw-w64-libunwind-svn
	mingw-w64-libusb-compat-git
	mingw-w64-libusb
	mingw-w64-libusbmuxd
	mingw-w64-libuv
	mingw-w64-libview
	mingw-w64-libvirt-glib
	mingw-w64-libvirt
	mingw-w64-libvisio
	mingw-w64-libvmime-git
	mingw-w64-libvorbis
	mingw-w64-libvorbisidec-svn
	mingw-w64-libvpx
	mingw-w64-libvterm-bzr
	mingw-w64-libwebp
	mingw-w64-libwebsockets
	mingw-w64-libwmf
	mingw-w64-libwpd
	mingw-w64-libwpg
	mingw-w64-libxlsxwriter
	mingw-w64-libxml++
	mingw-w64-libxml++2.6
	mingw-w64-libxml2
	mingw-w64-libxslt
	mingw-w64-libyaml
	mingw-w64-libzip
	mingw-w64-live-media
	mingw-w64-lmdb
	mingw-w64-lmdbxx
	mingw-w64-lua-bitop
	mingw-w64-lua-lgi
	mingw-w64-lua-lpeg
	mingw-w64-lua-lsqlite3
	mingw-w64-lua-luacom-git
	mingw-w64-lua-luarocks
	mingw-w64-lua-mpack
	mingw-w64-lua
	mingw-w64-lua51
	mingw-w64-luabind-git
	mingw-w64-luajit-git
	mingw-w64-luatex-svn
	mingw-w64-lz4
	mingw-w64-lzo2
	mingw-w64-m4
	mingw-w64-make
	mingw-w64-mathgl
	mingw-w64-matio
	mingw-w64-mbedtls
	mingw-w64-mcfgthread-git
	mingw-w64-mcpp
	mingw-w64-meanwhile
	mingw-w64-meld3
	mingw-w64-memphis
	mingw-w64-mesa
	mingw-w64-meson
	mingw-w64-metis
	mingw-w64-mhook
	mingw-w64-midori
	mingw-w64-miniupnpc
	mingw-w64-mlpack
	mingw-w64-mono-basic
	mingw-w64-mono
	mingw-w64-mpc
	mingw-w64-mpdecimal
	mingw-w64-mpfr
	mingw-w64-mpg123
	mingw-w64-mpv
	mingw-w64-msgpack-c
	mingw-w64-msmtp
	mingw-w64-mtex2MML
	mingw-w64-muparser
	mingw-w64-mypaint-git
	mingw-w64-mypaint
	mingw-w64-nanodbc
	mingw-w64-nanovg-git
	mingw-w64-nasm
	mingw-w64-ncurses
	mingw-w64-netcdf
	mingw-w64-nettle
	mingw-w64-nghttp2
	mingw-w64-ngraph-gtk
	mingw-w64-ngspice-git
	mingw-w64-ngspice
	mingw-w64-nim
	mingw-w64-nimble
	mingw-w64-ninja
	mingw-w64-nlopt
	mingw-w64-nodejs
	mingw-w64-npm
	mingw-w64-npth
	mingw-w64-nsis-nsisunz
	mingw-w64-nsis-svn
	mingw-w64-nsis
	mingw-w64-nspr
	mingw-w64-nss
	mingw-w64-ntldd-git
	mingw-w64-nutsnbolts-hg
	mingw-w64-nvidia-cg-toolkit
	mingw-w64-ocaml-camlp4
	mingw-w64-ocaml-findlib
	mingw-w64-ocaml-lablgtk
	mingw-w64-ocaml
	mingw-w64-oce
	mingw-w64-octave-hg
	mingw-w64-octopi-git
	mingw-w64-odt2txt
	mingw-w64-ogitor
	mingw-w64-ogre3d-hg
	mingw-w64-ogre3d
	mingw-w64-ogreassimp-hg
	mingw-w64-ois-git
	mingw-w64-ois
	mingw-w64-oniguruma
	mingw-w64-openal
	mingw-w64-openblas
	mingw-w64-opencl-headers
	mingw-w64-opencollada-git
	mingw-w64-opencolorio-git
	mingw-w64-opencore-amr
	mingw-w64-opencsg
	mingw-w64-opencv
	mingw-w64-openexr
	mingw-w64-openh264
	mingw-w64-openimageio
	mingw-w64-openjpeg
	mingw-w64-openjpeg2
	mingw-w64-openldap
	mingw-w64-openocd-git
	mingw-w64-openocd
	mingw-w64-openscad-git
	mingw-w64-openscad
	mingw-w64-openscenegraph
	mingw-w64-openshadinglanguage-git
	mingw-w64-openshadinglanguage
	mingw-w64-openssl
	mingw-w64-optipng
	mingw-w64-opus-git
	mingw-w64-opus-tools
	mingw-w64-opus
	mingw-w64-opusfile
	mingw-w64-orc
	mingw-w64-osgQt
	mingw-w64-osgQtQuick
	mingw-w64-osgbullet-git
	mingw-w64-osgearth-git
	mingw-w64-osgearth
	mingw-w64-osgocean-git
	mingw-w64-osgworks-git
	mingw-w64-osm-gps-map
	mingw-w64-osmgpsmap-git
	mingw-w64-osslsigncode
	mingw-w64-p11-kit
	mingw-w64-paho.mqtt.c
	mingw-w64-pango
	mingw-w64-pangomm
	mingw-w64-pathtools
	mingw-w64-pcre
	mingw-w64-pcre2
	mingw-w64-pdcurses
	mingw-w64-pdf2svg
	mingw-w64-pdfium-git
	mingw-w64-pdftex-svn
	mingw-w64-perl
	mingw-w64-phodav
	mingw-w64-physfs-hg
	mingw-w64-physfs
	mingw-w64-pidgin++-bzr
	mingw-w64-pidgin++
	mingw-w64-pidgin-hg
	mingw-w64-pidgin
	mingw-w64-pitivi-git
	mingw-w64-pixman
	mingw-w64-pkg-config
	mingw-w64-pkgconf
	mingw-w64-plplot
	mingw-w64-png2ico
	mingw-w64-pngcrush
	mingw-w64-pngnq
	mingw-w64-poco
	mingw-w64-podofo
	mingw-w64-polipo
	mingw-w64-poppler-data
	mingw-w64-poppler-qt4
	mingw-w64-poppler
	mingw-w64-popt
	mingw-w64-port-scanner
	mingw-w64-portablexdr
	mingw-w64-portaudio
	mingw-w64-portmidi
	mingw-w64-postgresql
	mingw-w64-postr
	mingw-w64-potrace
	mingw-w64-premake
	mingw-w64-profit-hg
	mingw-w64-proj
	mingw-w64-protobuf-c
	mingw-w64-protobuf
	mingw-w64-ptex
	mingw-w64-pugixml
	mingw-w64-purple-facebook-git
	mingw-w64-purple-facebook
	mingw-w64-purple-hangouts-hg
	mingw-w64-purple-skypeweb-git
	mingw-w64-purple-skypeweb
	mingw-w64-putty-git
	mingw-w64-putty-ssh
	mingw-w64-putty
	mingw-w64-pycairo
	mingw-w64-pygobject
	mingw-w64-pygobject2
	mingw-w64-pygtksourceview2
	mingw-w64-pyqt4
	mingw-w64-pyqt5
	mingw-w64-pyrex
	mingw-w64-pyside-qt4
	mingw-w64-pyside-tools-qt4
	mingw-w64-python-appdirs
	mingw-w64-python-asn1crypto
	mingw-w64-python-attrs
	mingw-w64-python-babel
	mingw-w64-python-beaker
	mingw-w64-python-beautifulsoup4
	mingw-w64-python-binwalk
	mingw-w64-python-bsddb3
	mingw-w64-python-certifi
	mingw-w64-python-cffi
	mingw-w64-python-characteristic
	mingw-w64-python-chardet
	mingw-w64-python-colorama
	mingw-w64-python-coverage
	mingw-w64-python-cryptography
	mingw-w64-python-cssselect
	mingw-w64-python-cvxopt
	mingw-w64-python-cx_Freeze
	mingw-w64-python-cycler
	mingw-w64-python-dateutil
	mingw-w64-python-decorator
	mingw-w64-python-distutils-extra
	mingw-w64-python-docutils
	mingw-w64-python-et-xmlfile
	mingw-w64-python-funcsigs
	mingw-w64-python-h5py
	mingw-w64-python-html5lib
	mingw-w64-python-httplib2
	mingw-w64-python-icu
	mingw-w64-python-idna
	mingw-w64-python-imagesize
	mingw-w64-python-ipykernel
	mingw-w64-python-ipython_genutils
	mingw-w64-python-jdcal
	mingw-w64-python-jinja
	mingw-w64-python-jsonschema
	mingw-w64-python-jupyter_client
	mingw-w64-python-jupyter_console
	mingw-w64-python-jupyter_core
	mingw-w64-python-lhafile
	mingw-w64-python-lxml
	mingw-w64-python-mako
	mingw-w64-python-markupsafe
	mingw-w64-python-matplotlib
	mingw-w64-python-mistune
	mingw-w64-python-mock
	mingw-w64-python-ndg-httpsclient
	mingw-w64-python-networkx
	mingw-w64-python-nose
	mingw-w64-python-nuitka
	mingw-w64-python-numexpr
	mingw-w64-python-numpy
	mingw-w64-python-olefile
	mingw-w64-python-openmdao
	mingw-w64-python-openpyxl
	mingw-w64-python-packaging
	mingw-w64-python-pandas
	mingw-w64-python-path
	mingw-w64-python-pathlib2
	mingw-w64-python-patsy
	mingw-w64-python-pbr
	mingw-w64-python-pdfrw
	mingw-w64-python-pgen2
	mingw-w64-python-pickleshare
	mingw-w64-python-pillow
	mingw-w64-python-pip
	mingw-w64-python-pluggy
	mingw-w64-python-pptx
	mingw-w64-python-pretend
	mingw-w64-python-prompt_toolkit
	mingw-w64-python-psutil
	mingw-w64-python-py
	mingw-w64-python-pyamg
	mingw-w64-python-pyasn1-modules
	mingw-w64-python-pyasn1
	mingw-w64-python-pycparser
	mingw-w64-python-pygments
	mingw-w64-python-pyopenssl
	mingw-w64-python-pyparsing
	mingw-w64-python-pytest
	mingw-w64-python-pytz
	mingw-w64-python-pywavelets
	mingw-w64-python-pywin32
	mingw-w64-python-pyzmq
	mingw-w64-python-qtconsole
	mingw-w64-python-reportlab
	mingw-w64-python-requests
	mingw-w64-python-rst2pdf
	mingw-w64-python-scandir
	mingw-w64-python-scipy
	mingw-w64-python-setuptools-scm
	mingw-w64-python-setuptools
	mingw-w64-python-simplegeneric
	mingw-w64-python-six
	mingw-w64-python-snowballstemmer
	mingw-w64-python-sphinx-alabaster-theme
	mingw-w64-python-sphinx
	mingw-w64-python-sphinx_rtd_theme
	mingw-w64-python-sphinxcontrib-websupport
	mingw-w64-python-sqlitedict
	mingw-w64-python-statsmodels
	mingw-w64-python-traitlets
	mingw-w64-python-urllib3
	mingw-w64-python-wcwidth
	mingw-w64-python-webencodings
	mingw-w64-python-whoosh
	mingw-w64-python-win_unicode_console
	mingw-w64-python-xlsxwriter
	mingw-w64-python-yaml
	mingw-w64-python-zope.event
	mingw-w64-python-zope.interface
	mingw-w64-python2-backports.shutil_get_terminal_size
	mingw-w64-python2-backports
	mingw-w64-python2-beautifulsoup3
	mingw-w64-python2-cjson
	mingw-w64-python2-enum
	mingw-w64-python2-enum34
	mingw-w64-python2-ipaddress
	mingw-w64-python2-ipython
	mingw-w64-python2-pygtk
	mingw-w64-python2-typing
	mingw-w64-python2
	mingw-w64-python3-ipython
	mingw-w64-python3
	mingw-w64-qbittorrent
	mingw-w64-qbs-git
	mingw-w64-qbs
	mingw-w64-qca-qt4-git
	mingw-w64-qca-qt5-git
	mingw-w64-qemu
	mingw-w64-qhttpengine
	mingw-w64-qhull-git
	mingw-w64-qjson-qt4
	mingw-w64-qmdnsengine
	mingw-w64-qpdf
	mingw-w64-qrencode
	mingw-w64-qrupdate-svn
	mingw-w64-qscintilla
	mingw-w64-qt-creator
	mingw-w64-qt-installer-framework-git
	mingw-w64-qt-solutions-git
	mingw-w64-qt3dstudio-git
	mingw-w64-qt4
	mingw-w64-qt5-git
	mingw-w64-qt5-static
	mingw-w64-qt5
	mingw-w64-qtbinpatcher
	mingw-w64-qtwebkit
	mingw-w64-quantlib
	mingw-w64-quarter-hg
	mingw-w64-quassel
	mingw-w64-quazip
	mingw-w64-qwt-qt4
	mingw-w64-qwt-qt5
	mingw-w64-qxmpp-qt4
	mingw-w64-qxmpp
	mingw-w64-rabbitmq-c
	mingw-w64-ragel
	mingw-w64-rapidjson
	mingw-w64-raptor2
	mingw-w64-rasqal
	mingw-w64-readline
	mingw-w64-readosm
	mingw-w64-recode
	mingw-w64-redland
	mingw-w64-remake-git
	mingw-w64-rhash
	mingw-w64-rtmpdump-git
	mingw-w64-rubberband
	mingw-w64-ruby-cairo
	mingw-w64-ruby-dbus
	mingw-w64-ruby-native-package-installer
	mingw-w64-ruby-pkg-config
	
	










FlatBuffers release 1.8.0
@aardappel aardappel released this on 21 Nov 2017 · 38 commits to master since this release

https://github.com/google/flatbuffers/
http://google.github.io/flatbuffers/flatbuffers_guide_building.html

#  FIX error: _WIN32_WINNT 0x0600; mingw32-make error: mutex in namespace std does not name a type; error: condition_variable in namespace  
#  Mutex, at least, is not supported in Thread model: win32 of the Mingw-builds toolchains. You could find in x86_64-4.9.2-posix-seh or newer
#  -----------------------------------------------------------------------------------------------------------------------------------------
#  Debug: -g2 -Wall Release: -O2 -Wno-error ///  -Wformat -Wformat-security
SET(CMAKE_MY_FLAGS 		${CMAKE_MY_FLAGS}	"-g2 -Wall -D_WIN32_WINNT=0x600 -pthread -static-libgcc -fexceptions -mtune=generic -pipe -fPIC -fomit-frame-pointer -fstack-protector-strong --param ssp-buffer-size=4 -D_FORTIFY_SOURCE=2") 
SET(CMAKE_C_FLAGS   	${CMAKE_MY_FLAGS}) 
SET(CMAKE_CXX_FLAGS   	${CMAKE_MY_FLAGS}	"-std=c++11 -static-libstdc++")
# for the gcc -fstack-protector* flags we need libssp
# clang does not have this
IF(CMAKE_COMPILER_IS_GNUCXX)
	SET(CMAKE_CXX_LINK_EXECUTABLE "${CMAKE_CXX_LINK_EXECUTABLE} -lssp")
	SET(CMAKE_C_LINK_EXECUTABLE   "${CMAKE_C_LINK_EXECUTABLE}   -lssp")
ENDIF()
#  -----------------------------------------------------------------------------------------------------------------------------------------


Building with CMake
The distribution comes with a cmake file that should allow you to build project/make files for any platform. For details on cmake, see http://www.cmake.org. In brief, depending on your platform, use one of e.g.:
cmake -G "Unix Makefiles"
cmake -G "Visual Studio 10"
cmake -G "Xcode"
-----------------------------------------------------------------------------
# Compiling the Monsters' Schema:
	cd bin
	flatc --cpp monster.fbs
	flatc --grpc --cpp greeter.fbs
	
-> general file: monster_generated.h, greeter.grpc.fb.cc, greeter.grpc.fb.h

# BUILD: 
	git clone https://github.com/google/flatbuffers.git
	cd flatbuffers
	cmake -G "MinGW Makefiles"   
	mingw32-make
	
# BUILD THIRD_PARTY: 

	cd third_party 
	git clone  zlib
	git clone  protobuf
	git clone  ssl
	git clone  gflags 
	
	cd third_party 
	cd cares 
	git clone  cares 
	
# BUILD boringssl: 	

	cd third_party
	cd boringssl
	cmake -DCMAKE_TOOLCHAIN_FILE=util/32-bit-toolchain.cmake -G "MinGW Makefiles"
	
# FIX error: _WIN32_WINNT 0x0600; error: mutex in namespace std does not name a type; error: condition_variable in namespace
	C:\mingw-w64-x86_64-7.2.0-win32-sjlj\mingw64\bin\g++.exe 
	C:\mingw-w64-x86_64-7.2.0-win32-sjlj\mingw64\bin\g++.exe -D_WIN32_WINNT=0x0601 -m32 -pthread -std=c++11 -static-libgcc
	C:\mingw-w64-x86_64-7.2.0-win32-sjlj\mingw64\bin\g++.exe -D_WIN32_WINNT=0x0601 -m32 -pthread -std=c++11 -static-libgcc
	
# TEST: build.bat:

	g++ sample_text.cpp -o text.exe -I"H:\flatbuffers-gcc72-mingw32\include" -L"H:\flatbuffers-gcc72-mingw32\lib" -lflatbuffers -static-libgcc -std=c++11
	g++ sample_binary.cpp -o binary.exe -I"H:\flatbuffers-gcc72-mingw32\include" -L"H:\flatbuffers-gcc72-mingw32\lib" -lflatbuffers -static-libgcc -std=c++11
	call binary.exe
	call text.exe
	
-----------------------------------------------------------------------------
If you want to do it manually, you can compile all your .cpp files into object files: g++ -c *.cpp
and link all the object files: g++ *.o -o a.out
If ClassA.cpp is changed, you can just recompile ClassA.cpp: g++ -c ClassA.cpp
and link them all again: g++ *.o -o a.out

For the #include, you are correct. Make sure you have include guards so that their contents are included only once.

#ifndef CLASS_A_H
#define CLASS_A_H

class classA
{

};

#endif
you can specify -o to g++ to name your output file something else than 'a.exe'

Usually with gcc/g++ and other command line compilers, the strategy is to first compile the source files, then link them with another command. This helps prevent the files not modified from being recompiled every time. This uses the -c switch of gcc

Try this

g++ -c ClassA.cpp -o ClassA.o
g++ -c ClassB.cpp -o ClassB.o
g++ -c main.cpp -o main.o

g++ ClassA.o ClassB.o main.o -o myProgram.exe
-----------------------------------------------------------------------------

Please learn about automake and autoconf.
Makefile.am is processed by automake to generate a Makefile that is processed by make in order to build your sources.
http://www.gnu.org/software/automake/

mingw32-make.exe makefile.in
make.exe makefile.in
-----------------------------------------------------------------------------
@echo off
CLS

::rm.exe -f main.o mutex-2.exe
::g++.exe -c main.cpp -o main.o -I"C:/Program Files (x86)/Dev-Cpp/MinGW64.GCC5.1.0/include" -I"C:/Program Files (x86)/Dev-Cpp/MinGW64.GCC5.1.0/x86_64-w64-mingw32/include" -I"C:/Program Files (x86)/Dev-Cpp/MinGW64.GCC5.1.0/lib/gcc/x86_64-w64-mingw32/5.1.0/include" -I"C:/Program Files (x86)/Dev-Cpp/MinGW64.GCC5.1.0/lib/gcc/x86_64-w64-mingw32/5.1.0/include/c++" -m32 -std=gnu++11
::g++.exe main.o -o mutex-2.exe -L"C:/Program Files (x86)/Dev-Cpp/MinGW64.GCC5.1.0/lib" -L"C:/Program Files (x86)/Dev-Cpp/MinGW64.GCC5.1.0/x86_64-w64-mingw32/lib" -static-libgcc -lmingw32 -m32

::g++ -I"C:/C++/protobuf.3.5.1-gcc.4.9.2/include" -L"C:/C++/protobuf.3.5.1-gcc.4.9.2/lib" main.cpp addressbook.pb.cc -lprotobuf -pthread

del /s /q /f *.o
del /s /q /f *.a
del /s /q /f *.dll
del /s /q /f *.exe
ECHO.
ECHO.

SET "CPP=g++.exe"

SET "GCC_LIB_PATH_1=C:/Program Files (x86)/Dev-Cpp/MinGW64.GCC5.1.0/lib"
SET "GCC_LIB_PATH_2=C:/Program Files (x86)/Dev-Cpp/MinGW64.GCC5.1.0/x86_64-w64-mingw32/lib"

SET "GCC_INCLUDE_PATH_1=C:/Program Files (x86)/Dev-Cpp/MinGW64.GCC5.1.0/include"
SET "GCC_INCLUDE_PATH_2=C:/Program Files (x86)/Dev-Cpp/MinGW64.GCC5.1.0/x86_64-w64-mingw32/include"
SET "GCC_INCLUDE_PATH_3=C:/Program Files (x86)/Dev-Cpp/MinGW64.GCC5.1.0/lib/gcc/x86_64-w64-mingw32/5.1.0/include"
SET "GCC_INCLUDE_PATH_4=C:/Program Files (x86)/Dev-Cpp/MinGW64.GCC5.1.0/lib/gcc/x86_64-w64-mingw32/5.1.0/include/c++"

SET "LIBS=-L"%GCC_LIB_PATH_1%" -L"%GCC_LIB_PATH_2%" -static-libgcc -m64"
SET "INCS=-I"%GCC_INCLUDE_PATH_1%" -I"%GCC_INCLUDE_PATH_2%" -I"%GCC_INCLUDE_PATH_3%""
SET "CXXINCS=-I"%GCC_INCLUDE_PATH_1%" -I"%GCC_INCLUDE_PATH_2%" -I"%GCC_INCLUDE_PATH_3%" -I"%GCC_INCLUDE_PATH_4%""

ECHO LIBS = %LIBS%
ECHO INCS = %INCS%
ECHO CXXINCS = %CXXINCS%

ECHO.
ECHO.

%CPP% -c main.cpp -o main.o -m32 -std=gnu++11 -D DF=123
::%CPP% main.o -o app.exe -m32 -static-libgcc -pthread -shared-libstdc++
%CPP% main.o -o app.exe -m32 -static-libgcc -pthread

::%CPP% -c addressbook.pb.cc -o addressbook.pb.o -I"C:/Program Files (x86)/Dev-Cpp/MinGW64/include" -I"C:/Program Files (x86)/Dev-Cpp/MinGW64/x86_64-w64-mingw32/include" -I"C:/C++/protobuf.3.5.1-gcc.4.9.2/include" -m32 -std=gnu++11
::%CPP% main.o addressbook.pb.o -o main.exe -L"C:/Program Files (x86)/Dev-Cpp/MinGW64/x86_64-w64-mingw32/lib32" -static-libgcc -L"C:/C++/protobuf.3.5.1-gcc.4.9.2/lib" -L"lib/libprotoc.a" -L"lib/libprotobuf.a" -m32

::%CPP% main.o -pthread
