SPK_NAME = minisatip
SPK_VERS = 2.84
SPK_REV = 11
SPK_ICON = src/minisatip.png
DSM_UI_DIR = app

DEPENDS = cross/busybox cross/$(SPK_NAME)

MAINTAINER = FatFred
DESCRIPTION = minisatip is an easy and fast satip client. You can control it remotely with its web interface or dedicated applications.
DESCRIPTION_FRE = minisatip est un client satip simple et rapide. Vous pouvez le contrôler à distance grâce à son interface web ou des applications dédiées.
DESCRIPTION_SPN = minisatip es un cliente satip simple y rápido. Puedes controlarlo remotamente mediante su interfaz web o alguna aplicación dedicada.
RELOAD_UI = yes
DISPLAY_NAME = minisatip
CHANGELOG = "First release"

HOMEPAGE = http://www.transmissionbt.com
LICENSE  = GPLv2/GPLv3

WIZARDS_DIR = src/wizard/

INSTALLER_SCRIPT = src/installer.sh
SSS_SCRIPT       = src/dsm-control.sh
FWPORTS          = src/${SPK_NAME}.sc

INSTALL_PREFIX = /usr/local/$(SPK_NAME)

POST_STRIP_TARGET = minisatip_extra_install

BUSYBOX_CONFIG = usrmng
ENV += BUSYBOX_CONFIG="$(BUSYBOX_CONFIG)"

include ../../mk/spksrc.spk.mk

.PHONY: minisatip_extra_install
minisatip_extra_install:
	install -m 755 -d $(STAGING_DIR)/var
	install -m 644 src/settings.json $(STAGING_DIR)/var/settings.json
	install -m 755 -d $(STAGING_DIR)/app
	install -m 644 src/app/config $(STAGING_DIR)/app/config
	install -m 755 -d $(STAGING_DIR)/app/images
	for size in 16 24 32 48 72 ; \
	do \
	    convert $(SPK_ICON) -thumbnail $${size}x$${size} \
	            $(STAGING_DIR)/app/images/$(SPK_NAME)-$${size}.png ; \
	done
