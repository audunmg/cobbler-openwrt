#
# Copyright (C) 2007-2011 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=koan
PKG_VERSION:=2017-03-22
PKG_RELEASE:=4
PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/cobbler/koan/
PKG_SOURCE_DATE:=2017-03-22
PKG_SOURCE_VERSION:=03b6e7facd0f9b959818fc8a76671a7341e85f57
PKG_MIRROR_HASH:=7d4457edc87e9ee7b9f765d18f172f3807f7c488844641cdcfc2913714b01874

include $(INCLUDE_DIR)/package.mk

define Package/koan
	SECTION:=admin
	CATEGORY:=Administration
	DEPENDS:=+python +python-netifaces
	TITLE:=Kickstart Over A Network
	URL:=http://github.com/cobbler/koan
endef

define Package/koan/description
  Kickstart over a network for cobbler
endef

define Package/koan/install
	$(INSTALL_DIR) $(PKG_BUILD_DIR)/koan $(1)/usr/lib/python2.7/koan 
	$(CP) $(PKG_BUILD_DIR)/koan/{app.py,cexceptions.py,configurator.py,imagecreate.py,__init__.py,openvzcreate.py,qcreate.py,register.py,utils.py,virtinstall.py,vmwcreate.py,xencreate.py} $(1)/usr/lib/python2.7/koan
	$(INSTALL_DIR) $(PKG_BUILD_DIR)/bin $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/bin/cobbler-register $(1)/usr/bin/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/bin/koan $(1)/usr/bin/
endef


$(eval $(call BuildPackage,koan))
