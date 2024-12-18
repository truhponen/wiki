---
title: Linux commands
description: 
published: true
date: 2024-12-18T10:45:21.266Z
tags: 
editor: markdown
dateCreated: 2024-12-18T10:40:49.644Z
---

### Size of directory

    du -sh /var

* s = only the total size
* h = sizes in a human-readable format
* /var - The path to the directory you want to get the size

### Compare directories

    diff -qr dir-1 dir-2

* report only differences
* recursive

### Count amount of files

    ls -l /oricopool-1/media/documents/photos | wc -l

### Run in background

https://linuxize.com/post/how-to-run-linux-commands-in-background/

### Find

Find all files that are over 100Mb

    find / -type f -size +100M