---
title: Desktop
date: '10:11 07-06-2026'
taxonomy:
    category:
        - docs
routes:
    default: /desktop
---

This page discribes the desktop computers setups. This is not related to homeautomation.

### ## Environment
* Distro: CachyOS
* Display manager: SDDM
* Window manager: Niri
* Shell: Dank Material Shell
* System manage: systemd
* Command line shell: fish shell

### Key apps
* Terminal: Alacritty
* File manager: Nautilus ("Files", Gnome)
* Browser: Microsoft Edge
* Package manager: Shelly
* Logitech utility: Solaar
* Admin UI: Cockpit client
* Text editor: Neovim
* Scanner utility: scangearmp2-sane-git + Simple scan

### Aditional apps
* Resource monitor: Btop++
* Image editing: GIMP
* SVG editing: Inkscpace
* PDF editing: Xournal++
* Image viewer: Loupe ("Image viewer", Gnome)

### Web apps
Web pages which can be launched with .desktop-files in browser without decorations. Idea is copied from [Omarchy](https://omarchy.org/).
* Personal browser: cc.kotimme.browser-personal.desktop
* Work browser: cc.kotimme.browser-work.desktop
* Google calendar: cc.kotimme.calendar.desktop
* Claude: cc.kotimme.claude.desktop
* FreshRSS: cc.kotimme.freshrss.desktop
* Gmail: cc.kotimme.gmail.desktop
* Home Assistant: cc.kotimme.homeassistant.desktop
* Homepage: cc.kotimme.homepage.desktop
* Helsingin Sanomat: cc.kotimme.hs.desktop
* Kubernes dashboard: cc.kotimme.kubernetes.desktop
* Let's Go Further web book: cc.kotimme.lets-go-further.desktop
* Google Sheets: cc.kotimme.sheets.desktop
* Spotify: cc.kotimme.spotify.desktop
* Telegram: cc.kotimme.telegram.desktop
* Whatsapp: cc.kotimme.whatsapp.desktop
* X: cc.kotimme.x.desktop
* Youtube: cc.kotimme.youtube.desktop

Script to add new browser app. Script is partially copied from [Omarchy](https://omarchy.org/).
* cc.kotimme.add-browser-app.desktop
* cc.kotimme.browser-app.desktop

### TUI apps
CLI apps which can be launched with .desktop-files in terminal. Idea is copied from [Omarchy](https://omarchy.org/).
* Disk usage: cc.kotimme.dust.desktop
* Kubernetes cluster: cc.kotimme.k9s.desktop

Script to add new TUI app. Script is partially copied from [Omarchy](https://omarchy.org/).
* cc.kotimme.add-tui-app.desktop