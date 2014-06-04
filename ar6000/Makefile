#------------------------------------------------------------------------------
# Copyright (c) 2004-2011 Atheros Communications Inc.
# Copyright (c) 2011-2012 Qualcomm Atheros, Inc.
# All rights reserved.
#
#
#
# Permission to use, copy, modify, and/or distribute this software for any
# purpose with or without fee is hereby granted, provided that the above
# copyright notice and this permission notice appear in all copies.
#
# THE SOFTWARE IS PROVIDED "AS IS" AND THE AUTHOR DISCLAIMS ALL WARRANTIES
# WITH REGARD TO THIS SOFTWARE INCLUDING ALL IMPLIED WARRANTIES OF
# MERCHANTABILITY AND FITNESS. IN NO EVENT SHALL THE AUTHOR BE LIABLE FOR
# ANY SPECIAL, DIRECT, INDIRECT, OR CONSEQUENTIAL DAMAGES OR ANY DAMAGES
# WHATSOEVER RESULTING FROM LOSS OF USE, DATA OR PROFITS, WHETHER IN AN
# ACTION OF CONTRACT, NEGLIGENCE OR OTHER TORTIOUS ACTION, ARISING OUT OF
# OR IN CONNECTION WITH THE USE OR PERFORMANCE OF THIS SOFTWARE.
#
#
#
# Author(s): ="Atheros"
#------------------------------------------------------------------------------

obj-m += ar6000.o
ar6000-y += debug.o
ar6000-y += debugfs_pri.o
ar6000-y += hif.o
ar6000-y += htc.o
ar6000-y += bmi.o
ar6000-y += cfg80211.o
ar6000-y += cfg80211_btcoex.o
ar6000-y += pm.o
ar6000-y += init.o
ar6000-y += main.o
ar6000-y += txrx.o
ar6000-y += wmi.o
ar6000-y += wmi_btcoex.o
ar6000-y += sdio.o
ar6000-y += platform.o
ar6000-y += softmac.o
ar6000-y += wmiconfig.o
ar6000-y += regd.o
ar6000-y += recovery.o
ar6000-y += testmode.o

ccflags-y += -D__CHECK_ENDIAN__
ccflags-y += -DCONFIG_ATH6KL_DEBUG
ccflags-y += -DCONFIG_CFG80211
ccflags-y += -DCONFIG_CFG80211_DEFAULT_PS
ccflags-y += -DCONFIG_CFG80211_WEXT
ccflags-y += -DCONFIG_NL80211_TESTMODE

ccflags-y += -DFIX_HUAWEI_BUTCHERING

ATH_ROOT = $(src)/..

ccflags-y += -I$(ATH_ROOT)/include
ccflags-y += -I$(ATH_ROOT)/ar6000
ccflags-y += -include $(ATH_ROOT)/include/linux/ieee80211.h
ccflags-y += -include $(ATH_ROOT)/include/linux/nl80211.h
ccflags-y += -include $(ATH_ROOT)/include/net/cfg80211.h
ccflags-y += -include $(ATH_ROOT)/include/linux/compat-2.6.h

ldflags-y += --strip-debug

KBUILD_EXTRA_SYMBOLS = $(ATH_ROOT)/cfg80211/Module.symvers

modules:
	$(MAKE) -C $(KERNEL_OUT) M=`pwd` ARCH=$(ARCH) CROSS_COMPILE=$(CROSS_COMPILE) modules

clean:
	$(MAKE) -C $(KERNEL_OUT) M=`pwd` ARCH=$(ARCH) CROSS_COMPILE=$(CROSS_COMPILE) clean
