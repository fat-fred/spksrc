PKG_NAME = minisatip
PKG_EXT = zip
PKG_DOWNLOAD_METHOD = git 
PKG_GIT_HASH = master
PKG_DIST_SITE = https://github.com/catalinii/minisatip/archive/$(PKG_GIT_HASH).$(PKG_EXT) 
PKG_DIST_FILE = $(PKG_GIT_HASH).$(PKG_EXT) 
PKG_DIR  = $(PKG_NAME)-$(PKG_GIT_HASH)

DEPENDS = cross/mcli cross/libdvbcsa

HOMEPAGE = http://www.transmissionbt.com/
COMMENT  = A Fast, Easy, and Free BitTorrent Client
LICENSE  =

CONFIGURE_TARGET = myConfigure
COMPILE_TARGET = myCompile
INSTALL_TARGET = myInstall
ADDITIONAL_CFLAGS = -I $(STAGING_INSTALL_PREFIX)/include/libxml2

include ../../mk/spksrc.cross-cc.mk

.PHONY: myConfigure
myConfigure: 

.PHONY: myCompile
myCompile:
	$(RUN) $(MAKE)

.PHONY: myInstall
myInstall:
	$(RUN) cp minisatip $(STAGING_INSTALL_PREFIX)/bin/