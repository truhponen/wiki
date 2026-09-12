---
title: PAM
date: '11:08 12-09-2026'
taxonomy:
    category:
        - docs
routes: {  }
---

Current greeter PAM-configuration.

   	#%PAM-1.0
	
	auth       required     pam_securetty.so
	auth       requisite    pam_nologin.so
	auth       include      system-local-login
	auth       optional     pam_gnome_keyring.so
	account    include      system-local-login
	session    include      system-local-login
	session    optional     pam_gnome_keyring.so auto_start

Following lines are needed to open gnome-keyring automatically

	auth       optional     pam_gnome_keyring.so
	session    optional     pam_gnome_keyring.so auto_start