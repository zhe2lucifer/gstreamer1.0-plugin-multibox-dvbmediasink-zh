glib_enum_prefix = gst_dvbsink

include glib-gen.mak

built_sources = gstdvbsink-marshal.c
built_headers = gstdvbsink-marshal.h

BUILT_SOURCES = $(built_sources) $(built_headers)
# plugindir is set in configure

CLEANFILES = $(BUILT_SOURCES)

EXTRA_DIST = gstdvbsink-marshal.list

plugin_LTLIBRARIES = libgstdvbvideosink.la libgstdvbaudiosink.la

# for the next set of variables, rename the prefix if you renamed the .la

# sources used to compile this plug-in
libgstdvbvideosink_la_SOURCES = common.c $(built_sources)
libgstdvbaudiosink_la_SOURCES = common.c $(built_sources)


# flags used to compile this plugin
# add other _CFLAGS and _LIBS as needed
libgstdvbvideosink_la_CFLAGS = $(GST_CFLAGS) $(GST_PLUGINS_BASE_CFLAGS) $(GST_BASE_CFLAGS) $(ORC_CFLAGS)
#libgstdvbvideosink_la_LIBADD = $(GST_LIBS) -lgstbase-$(GST_MAJORMINOR) $(GST_PLUGINS_BASE_LIBS) $(GST_BASE_LIBS) -laui
libgstdvbvideosink_la_LIBADD = ../git/obj/libgstdvbvideosink_la-gstdvbvideosink.lo $(GST_LIBS) -lgstbase-$(GST_MAJORMINOR) $(GST_PLUGINS_BASE_LIBS) $(GST_BASE_LIBS) @LIBAUI_LIBS@
#libgstdvbvideosink_la_LIBADD = $(GST_LIBS) -lgstbase-$(GST_MAJORMINOR) $(GST_PLUGINS_BASE_LIBS) $(GST_BASE_LIBS)
libgstdvbvideosink_la_LDFLAGS = $(GST_PLUGIN_LDFLAGS)

libgstdvbaudiosink_la_CFLAGS = $(GST_CFLAGS) $(GST_PLUGINS_BASE_CFLAGS) $(GST_BASE_CFLAGS) $(ORC_CFLAGS)
#libgstdvbaudiosink_la_LIBADD = $(GST_LIBS) -lgstbase-$(GST_MAJORMINOR) $(GST_PLUGINS_BASE_LIBS) $(GST_BASE_LIBS)
libgstdvbaudiosink_la_LIBADD = ../git/obj/libgstdvbaudiosink_la-gstdvbaudiosink.lo $(GST_LIBS) -lgstbase-$(GST_MAJORMINOR) $(GST_PLUGINS_BASE_LIBS) $(GST_BASE_LIBS) @LIBAUI_LIBS@
#libgstdvbaudiosink_la_LIBADD = $(GST_LIBS) -lgstbase-$(GST_MAJORMINOR) $(GST_PLUGINS_BASE_LIBS) $(GST_BASE_LIBS) -laui
libgstdvbaudiosink_la_LDFLAGS = $(GST_PLUGIN_LDFLAGS)

# headers we need but don't want installed
noinst_HEADERS = gstdvbvideosink.h gstdvbaudiosink.h gstdtsdownmix.h gstmpeg4p2unpack.h

plugin_LTLIBRARIES += libgstmpeg4p2unpack.la

libgstmpeg4p2unpack_la_SOURCES = gstmpeg4p2unpack.c

libgstmpeg4p2unpack_la_CFLAGS = $(GST_CFLAGS)
libgstmpeg4p2unpack_la_LIBADD = $(GST_LIBS) -lgstbase-$(GST_MAJORMINOR)
libgstmpeg4p2unpack_la_LDFLAGS = $(GST_PLUGIN_LDFLAGS)

if HAVE_DTSDOWNMIX
plugin_LTLIBRARIES += libgstdtsdownmix.la

libgstdtsdownmix_la_SOURCES = gstdtsdownmix.c common.c $(built_sources)

libgstdtsdownmix_la_CFLAGS = $(GST_CFLAGS) $(GST_PLUGINS_BASE_CFLAGS) $(GST_BASE_CFLAGS) $(ORC_CFLAGS)
libgstdtsdownmix_la_LIBADD = $(GST_LIBS) -lgstbase-$(GST_MAJORMINOR) $(DTS_LIBS) $(GST_PLUGINS_BASE_LIBS) $(GST_BASE_LIBS) -lgstaudio-$(GST_MAJORMINOR)
libgstdtsdownmix_la_LDFLAGS = $(GST_PLUGIN_LDFLAGS)
libgstdtsdownmix_la_LIBTOOLFLAGS = $(GST_PLUGIN_LIBTOOLFLAGS)
endif
