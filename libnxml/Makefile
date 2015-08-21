
#
# Copyright (C) 2010 Karl Zhang <356878@gmail.com>
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=libnxml
PKG_VERSION:=0.18.3
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://www.autistici.org/bakunin/$(PKG_NAME)
PKG_MD5SUM:=857f43970e7f0724d28f4ddc87085daf

PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/libnxml
  SECTION:=libs
  CATEGORY:=Libraries
  TITLE:=XML parse library
  URL:=http://www.autistici.org/bakunin/libnxml/doc/
  DEPENDS:=+libcurl
endef

define Package/libnxml/description
  nXML is a C library for parsing, writing and creating XML 1.0 and 1.1 files or streams. It supports utf-8, utf-16be and utf-16le, ucs-4 (1234, 4321, 2143, 2312).
endef

define Build/Configure
  $(call Build/Configure/Default,--enable-shared --enable-static)
endef

define Build/InstallDev
	mkdir -p $(1)/usr/include
	$(CP)	$(PKG_INSTALL_DIR)/usr/include/nxml.h \
		$(1)/usr/include/
	mkdir -p $(1)/usr/lib
	$(CP)	$(PKG_INSTALL_DIR)/usr/lib/libnxml.{a,so*} \
		$(1)/usr/lib/
	mkdir -p $(1)/usr/lib/pkgconfig
	$(CP)	$(PKG_INSTALL_DIR)/usr/lib/pkgconfig/nxml.pc \
		$(1)/usr/lib/pkgconfig/
endef

define Package/libnxml/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libnxml.so* $(1)/usr/lib/
endef

$(eval $(call BuildPackage,libnxml))
