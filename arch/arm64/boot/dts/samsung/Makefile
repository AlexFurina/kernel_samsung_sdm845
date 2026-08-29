dtb-$(CONFIG_MACH_STARQLTE_SINGLE) += starqlte/sdm845-sec-starqlte-r14.dtb

dtb-$(CONFIG_MACH_STARQLTE_KDI) += starqlte/sdm845-sec-starqlte-jpn-r14.dtb

dtb-$(CONFIG_MACH_STARQLTE_CHNZC) += starqlte/sdm845-sec-starqlte-chn-r14.dtb \
	starqlte/sdm845-sec-starqlte-chn-r14_v2.1.dtb

dtb-$(CONFIG_MACH_STAR2QLTE_SINGLE) += star2qlte/sdm845-sec-star2qlte-r14.dtb

dtb-$(CONFIG_MACH_STAR2QLTE_KDI) += star2qlte/sdm845-sec-star2qlte-jpn-r14.dtb

dtb-$(CONFIG_MACH_STAR2QLTE_CHNZC) += star2qlte/sdm845-sec-star2qlte-chn-r14.dtb \
	star2qlte/sdm845-sec-star2qlte-chn-r14_v2.1.dtb

dtb-$(CONFIG_MACH_CROWNQLTE_USA_SINGLE) += crownqlte/sdm845-sec-crownqlte-r10.dtb

dtb-$(CONFIG_MACH_CROWNQLTE_KDI) += crownqlte/sdm845-sec-crownqlte-jpn-r03.dtb

dtb-$(CONFIG_MACH_CROWNQLTE_CHNZC) += crownqlte/sdm845-sec-crownqlte-chn-r10.dtb

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
