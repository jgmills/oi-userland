#
# This file and its contents are supplied under the terms of the
# Common Development and Distribution License ("CDDL"), version 1.0.
# You may only use this file in accordance with the terms of version
# 1.0 of the CDDL.
#
# A full copy of the text of the CDDL should have accompanied this
# source.  A copy of the CDDL is also available via the Internet at
# http://www.illumos.org/license/CDDL.
#

#
# Copyright 2015 Aurelien Larcher
#

BUILD_BITS= 32_and_64
include ../../../make-rules/shared-macros.mk

COMPONENT_NAME= faad2
COMPONENT_VERSION= 2.7
COMPONENT_REVISION= 2
COMPONENT_SUMMARY= Open source MPEG-4 and MPEG-2 AAC decoder
COMPONENT_SRC= $(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE= $(COMPONENT_SRC).tar.gz
COMPONENT_ARCHIVE_HASH= \
	sha256:ee26ed1e177c0cd8fa8458a481b14a0b24ca0b51468c8b4c8b676fd3ceccd330
COMPONENT_ARCHIVE_URL=	https://downloads.sourceforge.net/project/faac/faad2-src/$(COMPONENT_SRC)/$(COMPONENT_ARCHIVE)
COMPONENT_PROJECT_URL = https://www.audiocoding.com/faad2.html	
COMPONENT_LICENSE = GPLv2
COMPONENT_LICENSE_FILE = $(COMPONENT_NAME).license
COMPONENT_CLASSIFICATION = Applications/Sound and Video
COMPONENT_FMRI = audio/faad2

TEST_TARGET=	$(NO_TESTS)
include $(WS_MAKE_RULES)/encumbered.mk
include $(WS_MAKE_RULES)/common.mk

COMPONENT_PREP_ACTION = (cd $(@D) ; autoreconf -if)

CFLAGS += $(CPP_LARGEFILES)

CONFIGURE_OPTIONS += --disable-static
CONFIGURE_OPTIONS += --without-drm
CONFIGURE_OPTIONS += --with-mpeg4ip

# Auto-generated dependencies
REQUIRED_PACKAGES += system/library
REQUIRED_PACKAGES += system/library/math
