#
# Copyright (C) 2019 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=omping
PKG_VERSION:=0.6-beta
PKG_RELEASE:=1
PKG_LICENSE:=GPL-2.0-or-later
PKG_LICENSE_FILES:=COPYING

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/jfriesse/omping.git
PKG_SOURCE_VERSION:=ea82ba7a43782901400934af3da7ef25e591f43a


include $(INCLUDE_DIR)/package.mk

define Package/omping
	SECTION:=net
	CATEGORY:=Network
	SUBMENU:=utils
	TITLE:=Omping (Open Multicast Ping) is tool to test IP multicast functionality primarily in local network.
	MAINTAINER:=Jan Friesse <jfriesse@redhat.com>
endef

define Package/omping/description
	Omping (Open Multicast Ping) is tool to test IP multicast functionality primarily in local network.
endef

define Package/omping/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/omping $(1)/usr/sbin/
endef

$(eval $(call BuildPackage,omping))