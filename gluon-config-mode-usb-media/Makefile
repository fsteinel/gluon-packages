include $(TOPDIR)/rules.mk

PKG_NAME:=gluon-config-mode-usb-media
PKG_VERSION:=1

PKG_BUILD_DIR := $(BUILD_DIR)/$(PKG_NAME)

include $(GLUONDIR)/include/package.mk

PKG_CONFIG_DEPENDS += $(GLUON_I18N_CONFIG)


define Package/gluon-config-mode-usb-media
  SECTION:=gluon
  CATEGORY:=Gluon
  TITLE:=Enable USB media and set web path for access
  DEPENDS:=gluon-config-mode-core-virtual +gluon-usb-media
endef

define Build/Prepare
	mkdir -p $(PKG_BUILD_DIR)
endef

define Build/Configure
endef

define Build/Compile
	$(call GluonBuildI18N,gluon-config-mode-usb-media,i18n)
endef

define Package/gluon-config-mode-usb-media/install
	$(CP) ./files/* $(1)/
	$(call GluonInstallI18N,gluon-config-mode-usb-media,$(1))
endef

$(eval $(call BuildPackage,gluon-config-mode-usb-media))
