include $(TOPDIR)/rules.mk

PKG_NAME:=vlmcsd
PKG_VERSION:=svn1113
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://codeload.github.com/Wind4/vlmcsd/tar.gz/$(PKG_VERSION)?
PKG_HASH:=62f55c48f5de1249c2348ab6b96dabbe7e38899230954b0c8774efb01d9c42cc

PKG_MAINTAINER:=fuyumi <280604399@qq.com>

PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk

define Package/vlmcsd
  SECTION:=net
  CATEGORY:=Network
  TITLE:=vlmcsd for OpenWRT
  DEPENDS:=+libpthread
endef

define Package/vlmcsd/description
  vlmcsd is a KMS Emulator in C.
endef

define Build/Prepare
	$(call Build/Prepare/Default)
	rm $(PKG_BUILD_DIR)/GNUmakefile
endef

define Package/vlmcsd/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/bin/vlmcsd $(1)/usr/bin/vlmcsd
	$(INSTALL_DIR) $(1)/etc/vlmcsd
	$(INSTALL_BIN) ./files/vlmcsd.ini $(1)/etc/vlmcsd/vlmcsd.ini
endef

$(eval $(call BuildPackage,vlmcsd))
