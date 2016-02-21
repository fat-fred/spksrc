PKG_NAME = mcli
PKG_EXT = tar.gz
PKG_DOWNLOAD_METHOD = git 
PKG_GIT_HASH = 0.9.0
PKG_DIST_SITE = https://projects.vdr-developer.org/attachments/download/1973/
PKG_DIST_FILE = vdr-$(PKG_NAME)-$(PKG_GIT_HASH).$(PKG_EXT) 

DEPENDS = cross/zlib cross/libxml2

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
	$(RUN) $(MAKE) -C $(PKG_NAME)-$(PKG_GIT_HASH)/mcast/client/ libmcli

.PHONY: myInstall
myInstall:
	$(RUN) cp $(PKG_NAME)-$(PKG_GIT_HASH)/mcast/client/libmcli.* $(STAGING_INSTALL_PREFIX)/lib/
	$(RUN) cp $(PKG_NAME)-$(PKG_GIT_HASH)/mcast/client/*.h $(STAGING_INSTALL_PREFIX)/include/
	$(RUN) cp $(PKG_NAME)-$(PKG_GIT_HASH)/mcast/common/*.h $(STAGING_INSTALL_PREFIX)/include/