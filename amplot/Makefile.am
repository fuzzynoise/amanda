# Makefile for amplot.

include $(top_srcdir)/config/automake/vars.am
include $(top_srcdir)/config/automake/scripts.am
include $(top_srcdir)/config/automake/installperms.am
include $(top_srcdir)/config/automake/precompile.am

SCRIPTS_SHELL = amplot
SCRIPTS_AWK = amcat.awk

sbin_SCRIPTS =		$(SCRIPTS_SHELL)
amplotdir =		$(amlibexecdir)
amplot_DATA =		$(SCRIPTS_AWK) amplot.awk amplot.g amplot.gp

EXTRA_DIST +=		amplot.awk		amplot.g

CLEANFILES += amplot.gp.new $(SCRIPTS_SHELL) $(SCRIPTS_AWK)
DISTCLEANFILES += amplot.gp config.log

amplot.gp: amplot.g
	cat $(srcdir)/amplot.g > amplot.gp.new
	echo "pause -1;" >> amplot.gp.new
	rm -f amplot.gp
	mv amplot.gp.new amplot.gp
