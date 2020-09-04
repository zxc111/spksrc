SPK_NAME = qbittorrent
SPK_VERS = 4.2.5
SPK_REV = 1
SPK_ICON = src/icon.png

BUILD_DEPENDS = cross/python cross/setuptools cross/pip cross/wheel
DEPENDS = cross/$(SPK_NAME)
SPK_DEPENDS = "python>=2.7.18"

REQUIRED_DSM = 6.1
# archs lacking C++11 compiler (88f6281, hi3535 and ppc archs except QorIQ) required by cross/libtorrent
UNSUPPORTED_ARCHS = 88f6281 hi3535 powerpc ppc824x ppc853x ppc854x

MAINTAINER = Strangelovian
DESCRIPTION = The qBittorrent project aims to provide an open-source software alternative to µTorrent. Additionally, qBittorrent runs and provides the same features on all major platforms (FreeBSD, Linux, macOS, OS/2, Windows). qBittorrent is based on the Qt toolkit and libtorrent-rasterbar library.
RELOAD_UI = yes
STARTABLE = yes
CHANGELOG = create syno community package with version 4.2.5
DISPLAY_NAME = qBitTorrent

HOMEPAGE = https://www.qbittorrent.org/
LICENSE  = GPL
HELPURL  = https://qbforums.shiki.hu/

# Custom start-stop script needed due to double-daemon
SSS_SCRIPT= src/dsm-control.sh

WIZARDS_DIR = src/wizard/

SERVICE_USER = auto
SERVICE_WIZARD_SHARE = wizard_download_dir
SERVICE_SETUP = src/service-setup.sh
SERVICE_PORT = 8112
SERVICE_PORT_TITLE = $(DISPLAY_NAME)

# Admin link for in DSM UI
ADMIN_PORT = $(SERVICE_PORT)

POST_STRIP_TARGET = qbittorrent_extra_install

include ../../mk/spksrc.spk.mk

.PHONY: qbittorrent_extra_install
deluge_extra_install:
	install -m 755 -d $(STAGING_DIR)/var
	install -m 644 src/core.conf $(STAGING_DIR)/var/core.conf
	install -m 644 src/autoadd.conf $(STAGING_DIR)/var/autoadd.conf
