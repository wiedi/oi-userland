#
# CDDL HEADER START
#
# The contents of this file are subject to the terms of the
# Common Development and Distribution License (the "License").
# You may not use this file except in compliance with the License.
#
# You can obtain a copy of the license at usr/src/OPENSOLARIS.LICENSE
# or http://www.opensolaris.org/os/licensing.
# See the License for the specific language governing permissions
# and limitations under the License.
#
# When distributing Covered Code, include this CDDL HEADER in each
# file and include the License file at usr/src/OPENSOLARIS.LICENSE.
# If applicable, add the following below this CDDL HEADER, with the
# fields enclosed by brackets "[]" replaced with your own identifying
# information: Portions Copyright [yyyy] [name of copyright owner]
#
# CDDL HEADER END
#
# Copyright (c) 2014, 2015, Oracle and/or its affiliates. All rights reserved.
#
include ../../../make-rules/shared-macros.mk

COMPONENT_NAME=		diffstat
COMPONENT_VERSION=	1.61
COMPONENT_FMRI=	text/diffstat
COMPONENT_SUMMARY=	A utility which provides statistics based on the output of diff
COMPONENT_CLASSIFICATION=	System/Text Tools
COMPONENT_PROJECT_URL=	http://invisible-island.net/diffstat/
COMPONENT_SRC=		$(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE=	$(COMPONENT_SRC).tgz
COMPONENT_ARCHIVE_HASH=	\
  sha256:25359e0c27183f997b36c9202583b5dc2df390c20e22a92606af4bf7856a55ee
COMPONENT_ARCHIVE_URL= \
  ftp://invisible-island.net/diffstat/$(COMPONENT_ARCHIVE)
COMPONENT_LICENSE=	MIT

include $(WS_MAKE_RULES)/prep.mk
include $(WS_MAKE_RULES)/configure.mk
include $(WS_MAKE_RULES)/ips.mk

CFLAGS += $(CPP_LARGEFILES)
CPPFLAGS += $(CPP_LARGEFILES)

CC += $(CC_BITS)

CONFIGURE_BINDIR.64 = $(CONFIGURE_BINDIR.32)

COMPONENT_TEST_DIR =	$(SOURCE_DIR)
COMPONENT_TEST_ENV =	PATH=$(@D):$(SOURCE_DIR):$(PATH)
COMPONENT_TEST_CMD =	./testing/run_test.sh
COMPONENT_TEST_ARGS =	./testing/case*.pat
COMPONENT_TEST_TARGETS =

COMPONENT_TEST_TRANSFORMS= \
	'-e "/Checking/d"'

ASLR_MODE = $(ASLR_ENABLE)

build:		$(BUILD_64)

install:	$(INSTALL_64)

test:		$(TEST_64)

# Auto-generated dependencies
# NONE
