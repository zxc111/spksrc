PKG_NAME = libqtbase
PKG_VERS = 5.12.9
PKG_EXT = tar.gz
PKG_DIST_NAME = v$(PKG_VERS).$(PKG_EXT)
PKG_DIST_SITE = https://github.com/qt/qtbase/archive
PKG_DIR = qtbase-$(PKG_VERS)

# cross/boost: archs lacking C++11 compiler (88f6281 and ppc archs except QorIQ)
UNSUPPORTED_ARCHS = 88f6281 powerpc ppc824x ppc853x ppc854x

HOMEPAGE = https://wiki.qt.io/Main
COMMENT  = Qt is a cross-platform application development framework for desktop, embedded and mobile.
LICENSE  = Qt open source license

CONFIGURE_ARGS += -extprefix $(INSTALL_DIR)/$(INSTALL_PREFIX)
CONFIGURE_ARGS += -hostprefix $(WORK_DIR)/hostbuild
CONFIGURE_ARGS += -device linux-generic-g++
CONFIGURE_ARGS += -device-option CROSS_COMPILE=/spksrc/toolchains/$(TC)/work/$(TC_TARGET)/bin/$(TC_PREFIX)
CONFIGURE_ARGS += -sysroot /spksrc/toolchains/$(TC)/work/$(TC_TARGET)/$(TC_TARGET)/sys-root
CONFIGURE_ARGS += -no-use-gold-linker -feature-dlopen -feature-library
CONFIGURE_ARGS += -no-gui -no-widgets -opensource -confirm-license -nomake examples
CONFIGURE_ARGS += -skip gui -skip widgets -skip testlib -skip concurrent -skip qtquickcontrols -skip qtwebkit -skip qtwebchannel -skip qtactiveqt -skip qtandroidextras -skip qtdeclarative -skip qtimageformats -skip qtmacextras -skip qtx11extras -skip qtxmlpatterns -skip qtconnectivity -skip qtdoc -skip qtenginio -skip qtgraphicaleffects -skip qtmultimedia -skip qtquick1 -skip qtsensors -skip qttranslations -skip qtwayland -skip qtwebchannel -skip qtwebengine -skip qtwebkit-examples -skip qtwebsockets -skip qtwinextras
CONFIGURE_ARGS += -verbose -no-gif -no-libjpeg -no-mtdev -no-sql-db2 -no-sql-ibase -no-sql-mysql -no-xcb -qt-freetype -no-fontconfig -no-harfbuzz -no-xcb-xlib -no-cups -no-icu -no-eglfs

include ../../mk/spksrc.cross-cc.mk
