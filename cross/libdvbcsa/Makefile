PKG_NAME = libdvbcsa
PKG_EXT = tar.gz
PKG_VERS = $(PKG_SVN_REV)
PKG_DOWNLOAD_METHOD = svn
PKG_SVN_REV = 20
PKG_DIST_NAME = trunk
PKG_DIST_SITE = svn://svn.videolan.org/libdvbcsa/
PKG_DIST_FILE = $(PKG_NAME)-r$(PKG_SVN_REV).$(PKG_EXT)
PKG_DIR = $(PKG_NAME)-r*

DEPENDS = cross/libtool

HOMEPAGE = https://www.gnu.org/software/libiconv
COMMENT  = iconv implementation
LICENSE  = GNU GPLv3

GNU_CONFIGURE = 1
CONFIGURE_TARGET = myConfigure

include ../../mk/spksrc.cross-cc.mk

.PHONY: myConfigure
myConfigure: 
	$(RUN) libtoolize --copy --force
	$(RUN) aclocal-1.14
	$(RUN) autoconf
	$(RUN) autoreconf -i
	$(RUN) autoheader
	$(RUN) automake-1.14 --foreign --add-missing --copy
	$(RUN) ./configure --host=x86_64