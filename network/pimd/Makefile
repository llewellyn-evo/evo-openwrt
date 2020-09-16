#
# Copyright (C) 2019 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=pimd
PKG_VERSION:=2.3.2
PKG_RELEASE:=1
PKG_LICENSE:=GPL-2.0-or-later
PKG_LICENSE_FILES:=COPYING

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/troglobit/pimd/releases/download/$(PKG_VERSION)
PKG_HASH:=a3c03e40540980b2c06e265a17988e60

PKG_FIXUP:=autoreconf

include $(INCLUDE_DIR)/package.mk

define Package/pimd
	SECTION:=net
	CATEGORY:=Network
	SUBMENU:=Routing and Redirection
	TITLE:=Dynamic Multicast Routing Daemon
	URL:=http://troglobit.com/pimd.html
	MAINTAINER:=Moritz Warning <moritzwarning@web.de>
endef

define Package/pimd/description
	Pimd is a command line tool to manipulate the multicast routes of the Linux kernel.
endef

define Package/pimd/conffiles
	/etc/pimd.conf
endef

#CONFIGURE_ARGS += \
#	--without-libcap

define Package/pimd/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_DIR) $(1)/etc/init.d/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/pimd $(1)/usr/sbin/
	$(INSTALL_CONF) $(PKG_BUILD_DIR)/pimd.conf $(1)/etc
	$(INSTALL_BIN) ./files/pimd.init $(1)/etc/init.d/pimd
endef

$(eval $(call BuildPackage,pimd))