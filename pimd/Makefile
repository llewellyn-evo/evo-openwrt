#
# Copyright (C) 2019 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=pimd
PKG_VERSION:=3.0-beta
PKG_RELEASE:=1
PKG_LICENSE:=GPL-2.0-or-later
PKG_LICENSE_FILES:=COPYING

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/troglobit/pimd.git
PKG_SOURCE_VERSION:=153bf84fd9f0b7e8372411e9940c5d28a37f3c1f

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

define Package/pimd/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/src/pimd $(1)/usr/sbin/
	$(INSTALL_DIR) $(1)/etc/config
	$(INSTALL_CONF) ./files/pimd $(1)/etc/config/
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) ./files/pimd.init $(1)/etc/init.d/pimd
endef

$(eval $(call BuildPackage,pimd))