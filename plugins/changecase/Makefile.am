# changecase plugin
plugindir = $(PLUMA_PLUGINS_LIBS_DIR)

INCLUDES = \
	-I$(top_srcdir) 				\
	$(PLUMA_CFLAGS) 				\
	$(WARN_CFLAGS)					\
	$(DISABLE_DEPRECATED_CFLAGS)

plugin_LTLIBRARIES = libchangecase.la

libchangecase_la_SOURCES = \
	pluma-changecase-plugin.h	\
	pluma-changecase-plugin.c

libchangecase_la_LDFLAGS = $(PLUGIN_LIBTOOL_FLAGS)
libchangecase_la_LIBADD = $(PLUMA_LIBS)

uidir = $(PLUMA_PLUGINS_DATA_DIR)/changecase
ui_DATA =

plugin_in_files = changecase.pluma-plugin.desktop.in

%.pluma-plugin: %.pluma-plugin.desktop.in $(INTLTOOL_MERGE) $(wildcard $(top_srcdir)/po/*po) ; $(INTLTOOL_MERGE) $(top_srcdir)/po $< $@ -d -u -c $(top_builddir)/po/.intltool-merge-cache

plugin_DATA = $(plugin_in_files:.pluma-plugin.desktop.in=.pluma-plugin)

EXTRA_DIST = $(ui_DATA) $(plugin_in_files)

CLEANFILES = $(plugin_DATA)
DISTCLEANFILES = $(plugin_DATA)


-include $(top_srcdir)/git.mk
