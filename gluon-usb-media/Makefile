include $(TOPDIR)/rules.mk

PKG_NAME:=gluon-usb-media
PKG_VERSION:=4
PKG_RELEASE:=$(GLUON_BRANCH)

PKG_BUILD_DIR := $(BUILD_DIR)/$(PKG_NAME)
PKG_BUILD_DEPENDS := respondd

include $(GLUONDIR)/include/package.mk

define Package/gluon-usb-media
  SECTION:=gluon
  CATEGORY:=Gluon
  DEPENDS:=+gluon-core +libgluonutil
  TITLE:=Automatically mount your USB media
endef

define Build/Prepare
	mkdir -p $(PKG_BUILD_DIR)
	$(CP) ./src/* $(PKG_BUILD_DIR)/
endef

define Package/gluon-usb-media/install
	$(CP) ./files/* $(1)/
endef

define Package/gluon-autoupdater/postinst
#!/bin/sh
$(call GluonCheckSite,check_site.lua)
endef

$(eval $(call BuildPackage,gluon-usb-media))
