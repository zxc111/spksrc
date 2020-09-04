PKG_NAME = qbittorrent
PKG_VERS = 4.2.5
PKG_EXT = tar.gz

PKG_DIST_NAME = release-$(PKG_VERS).$(PKG_EXT)
PKG_DIST_SITE = https://github.com/qbittorrent/qBittorrent/archive
PKG_DIR = qBittorrent-release-$(PKG_VERS)

DEPENDS = cross/libtorrent cross/libqt

HOMEPAGE = http://deluge-torrent.org/
COMMENT  = Deluge is a lightweight, Free Software, cross-platform BitTorrent client.
LICENSE  = MIT License

#CONFIGURE_TARGET = nop
#COMPILE_TARGET = nop
INSTALL_TARGET = qbittorrent_install


CONFIGURE_ARGS += QT_QMAKE=$(WORK_DIR)/hostbuild/bin
CONFIGURE_ARGS += --with-boost-system=boost_system
CONFIGURE_ARGS += --disable-gui

BOOST_LIBRARIES += system
ENV += BOOST_LIBRARIES="$(BOOST_LIBRARIES)"

include ../../mk/spksrc.cross-cc.mk

.PHONY: qbittorrent_install
deluge_install:
	mkdir -p $(STAGING_INSTALL_PREFIX)/share/qbittorrent
	tar -cf - -C $(WORK_DIR)/$(PKG_DIR) . | tar -xf - -C $(STAGING_INSTALL_PREFIX)/share/qbittorrent
