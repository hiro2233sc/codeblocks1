AM_CPPFLAGS = $(WX_CXXFLAGS) \
		$(WX_GTK_CFLAGS) \
		-I$(top_srcdir)/src/include \
		-I$(top_srcdir)/src/sdk/wxscintilla/include

pluginlibdir = $(pkglibdir)/plugins

pluginlib_LTLIBRARIES = libMouseSap.la

libMouseSap_la_LDFLAGS = @MODULE_SHARED_LDFLAGS@ -version-info 0:1:0 -no-undefined -avoid-version

libMouseSap_la_LIBADD = ../../../sdk/libcodeblocks.la $(WX_LIBS) $(WX_GTK_LIBS)

libMouseSap_la_SOURCES = MouseSap.cpp \
                         MouseSapCfg.cpp

noinst_HEADERS = MouseSap.h \
                 MouseSapCfg.h

EXTRA_DIST = $(srcdir)/*.cbp \
		manifest.xml

pkgdata_DATA = MouseSap.zip

CLEANFILES = $(pkgdata_DATA)

MouseSap.zip: manifest.xml
	PWD=`pwd` cd $(srcdir) && zip $(PWD)/MouseSap.zip manifest.xml > /dev/null
