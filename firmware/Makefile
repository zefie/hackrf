# Hey Emacs, this is a -*- makefile -*-
#
# Copyright 2012 Jared Boone <jared@sharebrained.com>
#
# This file is part of HackRF.
#
# This program is free software; you can redistribute it and/or modify
# it under the terms of the GNU General Public License as published by
# the Free Software Foundation; either version 2, or (at your option)
# any later version.
#
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
#
# You should have received a copy of the GNU General Public License
# along with this program; see the file COPYING.  If not, write to
# the Free Software Foundation, Inc., 51 Franklin Street,
# Boston, MA 02110-1301, USA.
#

TARGETS = blinky \
		  mixertx \
		  sgpio \
		  sgpio-rx \
		  simpletx \
		  startup \
		  startup_systick \
		  startup_systick_perfo \
		  hackrf_usb

all: build

build: examples

examples:
	$(Q)for i in $(TARGETS); do \
		if [ -d $$i ]; then \
			printf "  BUILD   $$i\n"; \
			$(MAKE) -C $$i || exit $?; \
		fi; \
	done

clean:
	$(Q)for i in $(addprefix lib/,$(TARGETS)) \
		     $(TARGETS); do \
		if [ -d $$i ]; then \
			printf "  CLEAN   $$i\n"; \
			$(MAKE) -C $$i clean || exit $?; \
		fi; \
	done

.PHONY: build examples
