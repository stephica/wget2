DEFS = @DEFS@ -DSYSCONFDIR=\"$(sysconfdir)/@PACKAGE@\" -DLOCALEDIR=\"$(localedir)\"

LDADD = $(LIBOBJS) ../lib/libgnu.a
AM_CFLAGS = $(WERROR_CFLAGS) $(WARN_CFLAGS)
AM_CPPFLAGS = -I$(top_srcdir)/include/wget -I$(srcdir) -I$(top_builddir)/lib -I$(top_srcdir)/lib \
 -DWGETVER_FILE=\"$(top_builddir)/include/wget/wgetver.h\" \
 -DWGET_PLUGIN_DIR=\"$(libdir)/wget2/plugins\"

bin_PROGRAMS = wget2 wget2_noinstall

wget2_SOURCES =\
 bar.c wget_bar.h\
 blacklist.c wget_blacklist.h\
 dl.c wget_dl.h\
 host.c wget_host.h\
 job.c wget_job.h\
 log.c wget_log.h\
 plugin.c wget_plugin.h\
 wget.c wget_main.h\
 options.c wget_options.h\
 wget_xattr.h

wget2_LDADD = ../libwget/libwget.la\
 $(LIBOBJS) $(GETADDRINFO_LIB) $(HOSTENT_LIB) $(INET_NTOP_LIB)\
 $(LIBSOCKET) $(LIB_CLOCK_GETTIME) $(LIB_NANOSLEEP) $(LIB_POLL) $(LIB_PTHREAD)\
 $(LIB_SELECT) $(LTLIBICONV) $(LTLIBINTL) $(LTLIBTHREAD) $(SERVENT_LIB) @INTL_MACOSX_LIBS@\
 $(LIBS) ../lib/libgnu.la

wget2_noinstall_SOURCES = $(wget2_SOURCES)
wget2_noinstall_LDFLAGS = -no-install
wget2_noinstall_LDADD = $(wget2_LDADD)

#css_tokenizer.c: $(srcdir)/css_tokenizer.lex css_tokenizer.h
#	$(LEX) -o $@ $<
