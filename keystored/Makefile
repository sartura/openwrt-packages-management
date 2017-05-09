# #
# # Copyright (C) 2016 OpenWrt.org
# #
# # This is free software, licensed under the GNU General Public License v2.
# # See /LICENSE for more information.
# #

# include $(TOPDIR)/rules.mk

# PKG_NAME:=keystored

# PKG_LICENSE:=BSD-3-Clause
# PKG_MAINTAINER:=Mislav Novakovic <mislav.novakovic@sartura.hr>

# PKG_VERSION:=0.1.1

# PKG_SOURCE_PROTO:=git
# PKG_SOURCE_VERSION:=b6dd154dd3a2215b91cfa7630682935dc9aa9460
# PKG_SOURCE:=$(PKG_NAME)-$(PKG_SOURCE_VERSION).tar.bz2
# PKG_SOURCE_URL:=https://github.com/CESNET/Netopeer2.git
# PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_SOURCE_VERSION)

# PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_SOURCE_SUBDIR)

# PKG_BUILD_PARALLEL:=1
# PKG_INSTALL:=1

# include $(INCLUDE_DIR)/package.mk
# include $(INCLUDE_DIR)/cmake.mk

# define Package/keystored
# 	SECTION:=util
# 	CATEGORY:=Utilities
# 	DEPENDS:=+sysrepod +sysrepoctl +sysrepocfg +libnetconf2 +openssl
# 	TITLE:=keystore for Netopeer2 server
# endef

# CMAKE_OPTIONS += \
# 	-DCMAKE_INSTALL_PREFIX=/usr \
# 	# -DCMAKE_BUILD_TYPE:STRING=release

# CMAKE_SOURCE_DIR=./keystored

# define Package/keystored/install
# 	$(INSTALL_DIR) $(1)/usr/lib/sysrepo/plugins
# 	$(INSTALL_BIN) $(PKG_BUILD_DIR)/libkeystored.so $(1)/usr/lib/sysrepo/plugins

# 	$(INSTALL_DIR) $(1)/etc/sysrepo/yang
# 	$(INSTALL_CONF) $(PKG_BUILD_DIR)/modules/ietf-keystore.yang $(1)/etc/sysrepo/yang
# endef

# 	# $(INSTALL_DIR) $(1)/etc/uci-defaults
# 	# $(INSTALL_BIN) ./files/netopeer2-server-yang.default $(1)/etc/uci-defaults/netopeer2-server

# $(eval $(call BuildPackage,keystored))
#
#
# Copyright (C) 2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_LICENSE:=BSD-3-Clause
PKG_MAINTAINER:=Mislav Novakovic <mislav.novakovic@sartura.hr>

PKG_NAME:=keystored
PKG_VERSION:=0.1.1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_VERSION:=b6dd154dd3a2215b91cfa7630682935dc9aa9460
PKG_SOURCE:=$(PKG_NAME)-$(PKG_SOURCE_VERSION).tar.bz2
PKG_SOURCE_URL:=https://github.com/CESNET/Netopeer2.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_SOURCE_VERSION)

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_SOURCE_SUBDIR)

PKG_BUILD_PARALLEL:=1
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/keystored
  SECTION:=util
  CATEGORY:=Utilities
  DEPENDS:=+sysrepod +sysrepoctl +sysrepocfg +libnetconf2 +openssl
  TITLE:=Netopeer2 server keystore
endef

CMAKE_OPTIONS += \
	-DCMAKE_INSTALL_PREFIX=/usr \
	-DCMAKE_BUILD_TYPE:STRING=release

CMAKE_SOURCE_DIR=./keystored

define Package/keystored/install
	$(INSTALL_DIR) $(1)/usr/lib/sysrepo/plugins
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/libkeystored.so $(1)/usr/lib/sysrepo/plugins
endef

$(eval $(call BuildPackage,keystored))
