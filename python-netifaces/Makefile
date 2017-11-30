#
# Copyright (C) 2007-2011 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python-netifaces
PKG_VERSION:=0_10_5
PKG_RELEASE:=1

PKG_SOURCE:=release_$(PKG_VERSION).tar.bz2
PKG_SOURCE_URL:=https://bitbucket.org/al45tair/netifaces/get/
PKG_HASH:=d181925a23842d1221d63cf3849dc7a554f8323bfb3eeb98ac152ff364560f75

PKG_BUILD_DEPENDS:=python python-setuptools

PKG_BUILD_DIR:=$(BUILD_DIR)/al45tair-netifaces-dc7c8e888476

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)


define Package/python-netifaces
	SECTION:=lang
	CATEGORY:=Languages
	SUBMENU:=Python
	DEPENDS:=+python
	TITLE:=Portable network interface information
	URL:=http://alastairs-place.net/projects/netifaces/
endef

define Package/python-netifaces/description
  netifaces provides a (hopefully portable-ish) way for Python programmers to
  get access to a list of the network interfaces on the local machine, and to
  obtain the addresses of those network interfaces.
endef

define Build/Compile
  $(call Build/Compile/PyMod,,install --prefix=/usr --root=$(PKG_INSTALL_DIR)) 
endef


$(eval $(call PyPackage,python-netifaces))
$(eval $(call BuildPackage,python-netifaces))
