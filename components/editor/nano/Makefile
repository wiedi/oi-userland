#
# This file and its contents are supplied under the terms of the
# Common Development and Distribution License ("CDDL)". You may
# only use this file in accordance with the terms of the CDDL.
#
# A full copy of the text of the CDDL should have accompanied this
# source. A copy of the CDDL is also available via the Internet at
# http://www.illumos.org/license/CDDL.
#

#
# Copyright (c) 2014 Rouven Wachhaus
#

include ../../../make-rules/shared-macros.mk

COMPONENT_NAME=		nano
COMPONENT_VERSION=	2.8.7
COMPONENT_FMRI=		editor/nano
COMPONENT_SUMMARY=	GNU implementation of nano, a text editor emulating pico
COMPONENT_CLASSIFICATION=System/Text Tools
COMPONENT_PROJECT_URL=	http://www.nano-editor.org/
COMPONENT_SRC=		$(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE=	$(COMPONENT_SRC).tar.gz
COMPONENT_ARCHIVE_HASH=	\
  sha256:a49a888c20f09a17c7f1049d1fda619472c92eedcb25fd4be5f088a51cc392a5
COMPONENT_ARCHIVE_URL=	http://ftp.gnu.org/pub/gnu/nano/$(COMPONENT_ARCHIVE)
COMPONENT_LICENSE=	GPLv3

include $(WS_MAKE_RULES)/prep.mk
include $(WS_MAKE_RULES)/configure.mk
include $(WS_MAKE_RULES)/ips.mk

COMPONENT_PREP_ACTION =        ( cd $(@D)  && autoreconf -fiv )


CONFIGURE_OPTIONS  +=		--enable-color
CONFIGURE_OPTIONS  +=		--enable-multibuffer
CONFIGURE_OPTIONS  +=		--enable-utf8
CONFIGURE_OPTIONS  +=		get_wch=getwch

CPPFLAGS += -I$(USRINCDIR)/ncurses
CFLAGS += -I$(USRINCDIR)/ncurses

# common targets
build:		$(BUILD_32)

install:	$(INSTALL_32)

test:		$(TEST_32)

REQUIRED_PACKAGES += library/ncurses
REQUIRED_PACKAGES += system/library
