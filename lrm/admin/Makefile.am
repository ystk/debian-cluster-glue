#
# Author: Sun Jiang Dong <sunjd@cn.ibm.com>
# Copyright (c) 2004 International Business Machines
#
# This program is free software; you can redistribute it and/or
# modify it under the terms of the GNU General Public License
# as published by the Free Software Foundation; either version 2
# of the License, or (at your option) any later version.
# 
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
# 
# You should have received a copy of the GNU General Public License
# along with this program; if not, write to the Free Software
# Foundation, Inc., 59 Temple Place - Suite 330, Boston, MA  02111-1307, USA.
#
MAINTAINERCLEANFILES = Makefile.in

INCLUDES 			=	-I$(top_builddir)/include -I$(top_srcdir)/include \
					-I$(top_builddir)/libltdl -I$(top_srcdir)/libltdl

halibdir			=	$(libdir)/@HB_PKG@
COMMONLIBS			=	$(top_builddir)/lib/clplumbing/libplumb.la $(GLIBLIB)
LRM_DIR			= 	lrm
sbin_PROGRAMS 		= 	lrmadmin
lrmadmin_SOURCES  	= 	lrmadmin.c
lrmadmin_LDFLAGS 	= 	$(COMMONLIBS)
lrmadmin_LDADD = $(top_builddir)/lib/$(LRM_DIR)/liblrm.la
lrmadmin_DEPENDENCIES = $(top_builddir)/lib/$(LRM_DIR)/liblrm.la

if BUILD_HELP
man8_MANS =	$(sbin_PROGRAMS:%=%.8)
%.8:	%
	echo Creating $@
	chmod a+x $<
	help2man --output $@ --no-info --section 8 --name "Part of the Linux-HA project" $(top_builddir)/lrm/admin/$<
endif
