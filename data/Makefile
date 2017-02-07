#
# Copyright (C) 2007-2011 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=snap7
PKG_VERSION:=1.4.2
PKG_RELEASE:=0

#PKG_SOURCE:=node-v$(PKG_VERSION).tar.gz
#PKG_SOURCE_URL:=https://snap7.org/dist/v$(PKG_VERSION)/
#PKG_MD5SUM:=5523ec4347d7fe6b0f6dda1d1c7799d5


PKG_INSTALL:=1
PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/host-build.mk
include $(INCLUDE_DIR)/package.mk

define Package/python-snap7
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages  
  TITLE:=python-snap7
  DEPENDS:=+libstdcpp +libpthread +librt +libc
endef

define Package/snap7/description
  Multi-platform Ethernet S7 PLC communication suite
endef


define Build/Prepare
  mkdir -p $(PKG_BUILD_DIR)/temp/
	$(CP) ./snap7-full-1.4.2/src/* $(PKG_BUILD_DIR)/
endef


define Build/Compile
  $(MAKE) -C $(PKG_BUILD_DIR) \
  CXX="$(TARGET_CROSS)g++"
endef

define Package/python-snap7/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/bin/out/libsnap7.so $(1)/usr/lib
endef


$(eval $(call HostBuild))
$(eval $(call BuildPackage,python-snap7))


