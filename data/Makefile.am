NULL =

SUBDIRS = appdata icons

migrationdir = $(datadir)/GConf/gsettings
dist_migration_DATA = org.gnome.packagekit.gschema.migrate

@INTLTOOL_DESKTOP_RULE@
desktopdir = $(datadir)/applications
desktop_in_files =					\
	pi-gpk-install-local-file.desktop.in		\
	pi-gpk-dbus-service.desktop.in			\
	pi-gpk-prefs.desktop.in				\
	pi-packages.desktop.in			\
	pi-gpk-update-viewer.desktop.in			\
	pi-gpk-log.desktop.in				\
	$(NULL)

desktop_DATA = $(desktop_in_files:.desktop.in=.desktop)

@INTLTOOL_DESKTOP_RULE@

pkgdata_DATA =						\
	pi-gpk-eula.ui					\
	pi-packages.ui				\
	pi-gpk-update-viewer.ui				\
	pi-gpk-prefs.ui					\
	pi-gpk-signature.ui				\
	pi-gpk-error.ui					\
	pi-gpk-log.ui					\
	pi-gpk-client.ui					\
	$(NULL)

servicedir = $(datadir)/dbus-1/services
service_in_files = org.freedesktop.PackageKit.service.in
service_DATA = $(service_in_files:.service.in=.service)

$(service_DATA): $(service_in_files) Makefile
	@sed -e "s|\@servicedir\@|$(bindir)|" $< > $@

@GSETTINGS_RULES@
gsettings_SCHEMAS = org.gnome.packagekit.gschema.xml

EXTRA_DIST =						\
	$(gsettings_SCHEMAS)				\
	$(autostart_in_files)				\
	$(desktop_in_files)				\
	$(pkgdata_DATA)					\
	$(service_in_files)				\
	$(NULL)

clean-local :
	rm -f *~

DISTCLEANFILES =					\
	pi-gpk-prefs.desktop				\
	pi-gpk-update-viewer.desktop			\
	pi-gpk-install-local-file.desktop			\
	pi-gpk-dbus-service.desktop			\
	pi-gpk-log.desktop					\
	pi-packages.desktop				\
	org.freedesktop.PackageKit.service		\
	$(NULL)

