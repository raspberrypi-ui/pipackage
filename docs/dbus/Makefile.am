
if ENABLE_GTK_DOC

all : org.rpi.pipackage.ref.xml

org.rpi.pipackage.ref.xml : $(top_srcdir)/src/org.rpi.pipackage.xml $(top_srcdir)/docs/dbus/spec-to-docbook.xsl
	echo "<?xml version=\"1.0\"?>""<!DOCTYPE refentry PUBLIC \"-//OASIS//DTD DocBook XML V4.1.2//EN\" \"http://www.oasis-open.org/docbook/xml/4.1.2/docbookx.dtd\">" > $@
	$(XSLTPROC) $(top_srcdir)/docs/dbus/spec-to-docbook.xsl $< | tail -n +2 >> $@

#$(top_srcdir)/docs/dbus/spec-to-docbook $(top_srcdir)/src/org.rpi.pipackage.xml

endif

EXTRA_DIST = spec-to-docbook.xsl dbus-introspect-docs.dtd

clean-local :
	rm -f *~ *.ref.xml
