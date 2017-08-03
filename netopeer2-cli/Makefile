#
# Copyright (C) 2017 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

# Warning by default OpenWrt does not have a root password which is necessery for NETCONF server.

include $(TOPDIR)/rules.mk

PKG_NAME:=netopeer2-cli

PKG_LICENSE:=BSD-3-Clause
PKG_MAINTAINER:=Mislav Novakovic <mislav.novakovic@sartura.hr>

PKG_VERSION:=0.4.0

PKG_SOURCE_PROTO:=git
PKG_SOURCE_VERSION:=d028c1f931819db4b3e3cb1fd2d349a4fd5c0459
PKG_MIRROR_HASH:=2e441554715cb0cd5f54bfb46aab0ab8d944c0e7d5084c7c1ff06e6542e7ab8d
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.xz
PKG_SOURCE_URL:=https://github.com/CESNET/Netopeer2.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION)

PKG_BUILD_ROOT:=$(BUILD_DIR)/$(PKG_SOURCE_SUBDIR)
PKG_BUILD_DIR:=$(PKG_BUILD_ROOT)

PKG_BUILD_PARALLEL:=1
PKG_INSTALL:=1

CMAKE_INSTALL:=1

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/netopeer2-cli
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=Netopeer2 cli tool
  URL:=$(PKG_SOURCE_URL)
  DEPENDS:=+libpthread +libyang +libnetconf2 +libopenssl
endef

define Package/netopeer2-cli/description
 Netopeer2 is a set of tools implementing network configuration tools based on the NETCONF
 Protocol. This is the second generation of the toolset, originally available as the Netopeer
 project. Netopeer2 is based on the new generation of the NETCONF and YANG libraries -
 libyang and libnetconf2. The Netopeer server uses sysrepo as a NETCONF datastore implementation.
endef

CMAKE_OPTIONS += \
	-DCMAKE_INSTALL_PREFIX:PATH=/usr \
	-DCMAKE_BUILD_TYPE:STRING=Release \
	-DKEYSTORED_KEYS_DIR:STRING=/etc/keystored/keys

CMAKE_SOURCE_DIR=./cli

define Package/netopeer2-cli/install
	$(INSTALL_DIR) $(1)/bin
	$(INSTALL_BIN) $(PKG_BUILD_ROOT)/netopeer2-cli $(1)/bin/
endef

$(eval $(call BuildPackage,netopeer2-cli))
