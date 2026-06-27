dtb-$(CONFIG_SEC_STARQLTE_PROJECT) += sdm845-sec-starqlte-r14.dtb	\

dtb-$(CONFIG_SEC_STAR2QLTE_PROJECT) += sdm845-sec-star2qlte-r14.dtb	\

dtb-$(CONFIG_SEC_CROWNQLTE_PROJECT) += sdm845-sec-crownqlte-r10.dtb	\

ifeq ($(filter y,$(CONFIG_MACH_STARQLTE_CHNZC))),y)
dtb-y = sdm845-sec-starqlte-chn-r14.dtb		\
	sdm845-sec-starqlte-chn-r14_v2.1.dtb
endif

ifeq ($(filter y,$(CONFIG_MACH_STAR2QLTE_CHNZC))),y)
dtb-y = sdm845-sec-star2qlte-chn-r14.dtb	\
	sdm845-sec-star2qlte-chn-r14_v2.1.dtb
endif

ifeq ($(filter y,$(CONFIG_MACH_CROWNQLTE_CHNZC))),y)
dtb-y =	sdm845-sec-crownqlte-chn-r10.dtb
endif

ifeq ($(CONFIG_ARM64),y)
always          := $(dtb-y)
subdir-y        := $(dts-dirs)
else
targets += dtbs
targets += $(addprefix ../, $(dtb-y))

$(obj)/../%.dtb: $(src)/%.dts FORCE
        $(call if_changed_dep,dtc)

dtbs: $(addprefix $(obj)/../,$(dtb-y))
endif
clean-files := *.dtb *.reverse.dts

