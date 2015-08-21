
#
# Copyright (C) 2010 Karl Zhang <356878@gmail.com>
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=libmrss
PKG_VERSION:=0.19.2
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://www.autistici.org/bakunin/$(PKG_NAME)
PKG_MD5SUM:=a6f66b72898d27270e3a68007f90d62b

# call 'make install' in the build dir
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/libmrss
  SECTION:=libs
  CATEGORY:=Libraries
  TITLE:=XML parse library
  URL:=http://www.autistici.org/bakunin/libnxml/doc/
  DEPENDS:=+libnxml +libcurl
endef

define Package/libmrss/description
  mRss is a C library for parsing, writing and creating RSS/ATOM files or streams.
endef

define Build/Configure
  $(call Build/Configure/Default,--enable-shared --enable-static)
endef

define Build/InstallDev
	mkdir -p $(1)/usr/include
	$(CP)	$(PKG_INSTALL_DIR)/usr/include/mrss.h \
		$(1)/usr/include/
	mkdir -p $(1)/usr/lib
	$(CP)	$(PKG_INSTALL_DIR)/usr/lib/libmrss.{a,so*} \
		$(1)/usr/lib/
	mkdir -p $(1)/usr/lib/pkgconfig
	$(CP)	$(PKG_INSTALL_DIR)/usr/lib/pkgconfig/mrss.pc \
		$(1)/usr/lib/pkgconfig/
endef

define Package/libmrss/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libmrss.so* $(1)/usr/lib/
endef

$(eval $(call BuildPackage,libmrss))
