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
# Copyright 2015 EveryCity Ltd. All rights reserved.
# Copyright 2016 Alexander Pyhalov
# Copyright 2016, 2017 Andreas Wacknitz
#

include ../../../make-rules/shared-macros.mk

COMPONENT_NAME=		node
COMPONENT_FMRI=		runtime/nodejs-6
COMPONENT_SUMMARY=	Evented I/O for V8 JavaScript.
COMPONENT_CLASSIFICATION=	Development/Other Languages
COMPONENT_PROJECT_URL=	http://nodejs.org
COMPONENT_VERSION=	6.11.3
COMPONENT_REVISION=	1
COMPONENT_LICENSE=	BSD-like, MIT, Apache
COMPONENT_LICENSE_FILE=	node.license	
COMPONENT_SRC=		$(COMPONENT_NAME)-v$(COMPONENT_VERSION)
COMPONENT_ARCHIVE=	$(COMPONENT_SRC).tar.gz
COMPONENT_ARCHIVE_HASH=	sha256:c60562a7bc316f137297b7aa23ae354e3ac6779fe8ddf46fe43a75b6b92443e8
COMPONENT_ARCHIVE_URL=	http://nodejs.org/dist/v$(COMPONENT_VERSION)/$(COMPONENT_ARCHIVE)

include $(WS_MAKE_RULES)/prep.mk
include $(WS_MAKE_RULES)/configure.mk
include $(WS_MAKE_RULES)/ips.mk

# Include /usr/sbin for dtrace
PATH=$(PATH.gnu)

CONFIG_SHELL =	$(PYTHON)

COMPONENT_PRE_CONFIGURE_ACTION = ($(CLONEY) $(SOURCE_DIR) $(@D))

CONFIGURE_SCRIPT =	$(@D)/configure

CONFIGURE_OPTIONS= --prefix=/usr/node/6

build:		$(BUILD_32)

install:	$(INSTALL_32)

REQUIRED_PACKAGES += SUNWcs
REQUIRED_PACKAGES += system/library
REQUIRED_PACKAGES += system/library/g++-4-runtime
REQUIRED_PACKAGES += system/library/math

