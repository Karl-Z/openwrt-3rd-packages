#
# Copyright (C) 2010 Karl Zhang <356878@gmail.com>
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=libcii
PKG_VERSION:=1.2
PKG_RELEASE:=1

#PKG_SOURCE:=master.zip
#PKG_SOURCE_URL:=https://github.com/kev009/cii/archive
#PKG_MD5SUM:=cff35b38267aa2c3f965f39e8dde61c2

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/kev009/cii.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=4af8d6185f
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.gz

# call 'make install'
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/libcii
  SECTION:=libs
  CATEGORY:=Libraries
  TITLE:=Basic C library
  URL:=https://github.com/kev009/cii
endef

define Package/libcii/description
  This hierarchy contains all the source code from the book "C Interfaces and Implementations: Techniques for Creating Reusable Software (Addison-Wesley Professional Computing Series, 1997, ISBN 0-201-49841-3)."
endef

define Build/Compile
	$(call Build/Compile/Default,THREADS= EXAMPLES=)
endef
define Build/Install
	$(call Build/Install/Default,install PREFIX=/usr)
endef

define Build/InstallDev
	mkdir -p $(1)/usr/include
	$(CP) -r	$(PKG_INSTALL_DIR)/usr/include/cii \
		$(1)/usr/include/
	mkdir -p $(1)/usr/lib
	$(CP)	$(PKG_INSTALL_DIR)/usr/lib/libcii.{a,so*} \
		$(1)/usr/lib/
endef
	
define Package/libcii/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libcii.so.* $(1)/usr/lib/
endef

$(eval $(call BuildPackage,libcii))
