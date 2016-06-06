#
# Copyright (C) 2006-2014 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=libstk
PKG_VERSION:=4.5.1
PKG_RELEASE:=1

PKG_BUILD_DIR:=$(BUILD_DIR)/libstk

PKG_LICENSE:=PERMISSIVE

include $(INCLUDE_DIR)/package.mk

define Package/libstk
  SECTION:=libs
  CATEGORY:=Libraries
  DEPENDS:=+lpthread +alsa-lib +lm +uclibcxx
  TITLE:=The Synthesis Toolkit in C++
  URL:=https://github.com/thestk/stk
endef

define Package/libstk/description
 This package contains a library for The Synthesis Toolkit in C++
endef

LIBS:=-nodefaultlibs -lgcc -lc -luClibc++ -lm -lpthread -lasound 

define Build/Prepare
	mkdir -p $(PKG_BUILD_DIR)
	$(CP) ./stk/* $(PKG_BUILD_DIR)/
endef

define Package/libstk/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_BUILD_DIR)/src/libstk.a $(1)/usr/lib/
	$(CP) $(PKG_BUILD_DIR)/src/libstk.so $(1)/usr/lib/
	$(CP) $(PKG_BUILD_DIR)/src/libstk-$(PKG_VERSION).so $(1)/usr/lib/
endef

$(eval $(call BuildPackage,libstk))
