# Copyright (C) 2015 PSP2SDK Project
#
# This Source Code Form is subject to the terms of the Mozilla Public
# License, v. 2.0. If a copy of the MPL was not distributed with this
# file, You can obtain one at http://mozilla.org/MPL/2.0/.

include $(top_srcdir)/stubs/common.mk

PREFIX = _SceSha1-0001_
ENTRIES_PREFIX = $(PREFIX)F00_

NIDS = 0x0195dadf 0x9007205e 0xb13d65aa 0xe1215c9d

ENTRIES = $(call GET_ENTRIES,$(ENTRIES_PREFIX),$(NIDS))

lib_LIBRARIES = libSceSha1_stub.a
libSceSha1_stub_a_SOURCES = SceSha1_stub.S
am_libSceSha1_stub_a_OBJECTS = $(call GET_OBJECTS,$(PREFIX),$(ENTRIES))

$(PREFIX)head.o: $(libSceSha1_stub_a_SOURCES)
	$(COMPILE_HEAD)

$(PREFIX)NIDS.o: $(libSceSha1_stub_a_SOURCES)
	$(COMPILE_NIDS)

$(ENTRIES): $(libSceSha1_stub_a_SOURCES)
	$(call COMPILE_ENTRIES,$(ENTRIES_PREFIX))
