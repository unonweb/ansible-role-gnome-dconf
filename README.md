EXAMPLE
=======

```yml
# gnome-dconf
- ansible.builtin.import_role:
	name: gnome-dconf
	vars:
	gnome_dconf_user: frida
	gnome_dconf_configs:
		# tracker
	- key: /org/freedesktop/tracker/miner/files/index-optical-discs
		value: "false"
		# calculator
	- key: /org/gnome/calculator/refresh-interval
		value: "0"
		# file-chooser
	- key: /org/gtk/settings/file-chooser/sort-directories-first
		value: "true"
		# media-keys
	- key: /org/gnome/settings-daemon/plugins/media-keys/volume-up
		value: "['<Super>KP_Add']"
	- key: /org/gnome/settings-daemon/plugins/media-keys/volume-down
		value: "['<Super>KP_Subtract']"
		# media-handling
	- key: /org/gnome/desktop/media-handling/autorun-never # If true, then Nautilus will never prompt nor autorun/autostart programs when a medium is inserted
		value: "false"
		# power
	- key: "/org/gnome/settings-daemon/plugins/power/sleep-inactive-ac-timeout" # The amount of time in seconds the computer on AC power needs to be inactive before it goes to sleep.
		value: "0"
	- key: "/org/gnome/settings-daemon/plugins/power/sleep-inactive-ac-type"
		value: "'nothing'"
	- key: /org/gnome/settings-daemon/plugins/power/sleep-inactive-battery-type # Whether to hibernate, suspend or do nothing when inactive
		value: "'suspend'"
	- key: /org/gnome/settings-daemon/plugins/power/idle-dim # If the screen should be dimmed to save power when the computer is idle
		value: "true"
		# screensaver
	- key: /org/gnome/desktop/screensaver/lock-enabled # If true the screen locks when the screensaver goes active
		value: "false"
		# session
	- key: /org/gnome/desktop/session/idle-delay # Number of seconds of inactivity before the session is considered idle
		value: "0"
		# privacy
	- key: /org/gnome/desktop/privacy/remove-old-temp-files # Whether to remove old temporary files automatically
		value: "true"
	- key: /org/gnome/desktop/privacy/remove-old-trash-files # Whether to remove old files from the trash automatically
		value: "true"
	- key: /org/gnome/desktop/privacy/old-files-age # Number of days to keep trash and temporary files
		value: "7"
	- key: /org/gnome/shell/remember-mount-password
		value: "false" # keine cryptsetup passwörter speichern
```

NOTES
=====

idle - screensaver - lock
--------------------------

In Gnome the screensaver typically activates when the session is idle, and the screen lock happens when the screensaver is active