---
title: Desktop
date: '10:11 07-06-2026'
taxonomy:
    category:
        - docs
routes:
    default: /desktop
---

This page discribes the desktop computers setups. This is not really related to homeautomation.

### CachyOS 
* Boot loader
	* Limine (own background)
* Disk partion
	* /boot: 4G
	* / (root): 50G
	* /home: the rest
	* No swap partition
* No Desktop
* System manager
	* systemd
		* systemctl --global add-wants niri.service dms
		* systemctl --user add-wants dms.service shelly-notifications
* Command line shell
	* fish
* Package manager
	* Pacman + Shelly

### Display manager
* SDDM
* SDDM theme: Silent (own dotfiles and background)

### Configs and shared assets 
* dotfiles
   	* /home/dotfiles/...
* Browser & TUI apps
	* /home/dotfiles/usr/share/applications
* Wallpapers
	* /home/wallpapers
* Application icon
   	* /home/dotfiles/usr/share/icons/hicolor/512x512/apps/

### Desktop
* Window manager
	* Niri (dotfiles)
* Shell
	* Dank Material Shell (dotfiles)
* Screenshots
	* grim
	* slurp
	* satty (dotfiles)
* Logitech utility
	* Solaar (dotfiles)
* Terminal
	* Alacritty
* File manager
	* Nautilus ("Files", Gnome)
* Image viewer
   	* Loupe ("Image viewer", Gnome)
* Browser:
	* Microsoft Edge

### Other Apps
* Admin UI
	* Cockpit client (Browser app)
* Text editor
	* Neovim
* Scanner utility
	* scangearmp2-sane-git + Simple scan
* Resource monitor
	* Btop++ (TUI app)
* Image editing
	* GIMP
* SVG editing
	* Inkscpace

### Web apps
Web pages which can be launched with .desktop-files in browser without decorations. Idea is copied from [Omarchy](https://omarchy.org/).
* Personal browser
	* cc.kotimme.browser-personal.desktop
* Work browser
	* cc.kotimme.browser-work.desktop
* Google calendar
	* cc.kotimme.calendar.desktop
* Claude
	* cc.kotimme.claude.desktop
* FreshRSS
	* cc.kotimme.freshrss.desktop
* Gmail
	* cc.kotimme.gmail.desktop
* Home Assistant
	* cc.kotimme.homeassistant.desktop
* Homepage
	* cc.kotimme.homepage.desktop
* Helsingin Sanomat
	* cc.kotimme.hs.desktop
* Kubernes dashboard
	* cc.kotimme.kubernetes.desktop
* Let's Go Further web book
	* cc.kotimme.lets-go-further.desktop
* Google Sheets
	* cc.kotimme.sheets.desktop
* Spotify
	* cc.kotimme.spotify.desktop
* Telegram
	* cc.kotimme.telegram.desktop
* Whatsapp
	* cc.kotimme.whatsapp.desktop
* X
	* cc.kotimme.x.desktop
* Youtube
	* cc.kotimme.youtube.desktop

Scripts to add new browser app. Script is partially copied from [Omarchy](https://omarchy.org/).
* cc.kotimme.add-browser-app.desktop

Scripts use common "cc.kotimme.browser-app.desktop" browser app to launch.

### TUI apps
CLI apps which can be launched with .desktop-files in terminal. Idea is copied from [Omarchy](https://omarchy.org/).
* Disk usage: cc.kotimme.dust.desktop
* Kubernetes cluster: cc.kotimme.k9s.desktop

Script to add new TUI app. Script is partially copied from [Omarchy](https://omarchy.org/).
* cc.kotimme.add-tui-app.desktop