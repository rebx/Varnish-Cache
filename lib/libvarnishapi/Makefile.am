#

INCLUDES = -I$(top_srcdir)/include @PCRE_CFLAGS@

lib_LTLIBRARIES = libvarnishapi.la

libvarnishapi_la_LDFLAGS = -version-info 1:0:0

libvarnishapi_la_SOURCES = \
	vsm_api.h \
	vsl_api.h \
	\
	../libvarnish/vas.c \
	../libvarnish/vav.c \
	../../include/vcs_version.h \
	../libvarnish/version.c \
	../libvarnish/cli_common.c \
	../libvarnish/cli_auth.c \
	../libvarnish/vin.c \
	../libvarnish/vmb.c \
	../libvarnish/vre.c \
	../libvarnish/vsb.c \
	../libvarnish/vsha256.c \
	vsm.c \
	vsl_arg.c \
	vsl.c \
	vsc.c \
	libvarnishapi.map

libvarnishapi_la_CFLAGS = \
	-DVARNISH_STATE_DIR='"${VARNISH_STATE_DIR}"'

libvarnishapi_la_LIBADD = @PCRE_LIBS@

if HAVE_LD_VERSION_SCRIPT
libvarnishapi_la_LDFLAGS += -Wl,--version-script=$(srcdir)/libvarnishapi.map
else
libvarnishapi_la_LDFLAGS += -export-symbols-regex '^V'
endif
