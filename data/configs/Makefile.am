dbusdir = $(datadir)/dbus-1/system.d
dbus_DATA = org.blueman.Mechanism.conf

dbus_servicesdir = $(datadir)/dbus-1/system-services
dbus_services_DATA = org.blueman.Mechanism.service

dbus_sessdir = $(datadir)/dbus-1/services
dbus_sess_DATA = org.blueman.Applet.service

if SYSTEMD_SYSTEM_UNIT_DIR
systemd_systemdir = $(systemd_system_unit_dir)
systemd_system_DATA = blueman-mechanism.service
endif

if SYSTEMD_USER_UNIT_DIR
systemd_userdir = $(systemd_user_unit_dir)
systemd_user_DATA = blueman-applet.service
endif

if HAVE_POLKIT
policykitactionsdir = $(datadir)/polkit-1/actions
policykitactions_DATA = org.blueman.policy

org.blueman.policy: org.blueman.policy.in
	$(AM_V_GEN) GETTEXTDATADIR=$(top_srcdir)/data/configs $(MSGFMT) --xml -d $(top_srcdir)/po/ -o $@ --template $<


policykitrulesdir = $(datadir)/polkit-1/rules.d
policykitrules_DATA = blueman.rules
endif

EXTRA_DIST = \
	its 					\
	blueman-applet.service.in		\
	blueman-mechanism.service.in		\
	org.blueman.Mechanism.conf		\
	org.blueman.Applet.service.in		\
	org.blueman.Mechanism.service.in	\
	org.blueman.policy.in			\
	blueman.rules

CLEANFILES =		\
	blueman-applet.service		\
	blueman-mechanism.service	\
	org.blueman.Mechanism.service	\
	org.blueman.Applet.service		\
	org.blueman.policy		\
	$(BUILT_SOURCES)

DISTCLEANFILES = \
	$(CLEANFILES)

