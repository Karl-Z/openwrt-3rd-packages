#
# Copyright (C) 2010 Karl Zhang <356878@gmail.com>
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=seedget
PKG_VERSION:=0.1
PKG_RELEASE:=1

#PKG_SOURCE:=master.zip
#PKG_SOURCE_URL:=https://github.com/kev009/cii/archive
#PKG_MD5SUM:=cff35b38267aa2c3f965f39e8dde61c2

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://gitlab.com/Karl.Z/c-projects.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=21f24ab1
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.gz

# call 'make install'
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/seedget
  SECTION:=net
  CATEGORY:=Network
  TITLE:=Seed download tool
  URL:=https://gitlab.com/Karl.Z/c-projects
  DEPENDS:=+libmrss +libcurl +libcii +zlib
endef

define Package/seedget/description
  This tool is used to download seed file from RSS feeds.
endef

#PKG_BUILD_DEPENDS:=libcii
#PKG_DEPENDS:=+libmrss +libcurl +libcii

define Build/Prepare
	$(PKG_UNPACK)
	mv -f $(PKG_BUILD_DIR)/seedget/* $(PKG_BUILD_DIR)
	rm -rf $(PKG_BUILD_DIR)/seedget
endef

define Build/Configure
	$(call Build/Configure/Default)
endef

define Build/Compile
	$(call Build/Compile/Default)
endef

define Package/seedget/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/seedget $(1)/usr/bin
endef

$(eval $(call BuildPackage,seedget))
