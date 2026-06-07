---
title: 'How to remove “You do not have a valid subscription for this server”'
date: '21:08 22-12-2024'
taxonomy:
    category:
        - docs
---

Instructions copied from Roaster-Dude https://www.reddit.com/r/Proxmox/comments/tgojp1/removing_proxmox_subscription_notice/?share_id=S5V91w5M7jBQ7jAn2bnwn&utm_content=2&utm_medium=android_app&utm_name=androidcss&utm_source=share&utm_term=14

Similar instruction are available also in https://dannyda.com/2020/05/17/how-to-remove-you-do-not-have-a-valid-subscription-for-this-server-from-proxmox-virtual-environment-6-1-2-proxmox-ve-6-1-2-pve-6-1-2/

### Steps

1. Login to proxmox server.
2. Change folder 

        cd /usr/share/javascript/proxmox-widget-toolkit

3. Backup file 

        cp proxmoxlib.js proxmoxlib.js.bak

4. Edit file  

        nano proxmoxlib.js

5. Change `.data.status.toLowerCase() !== 'active')` to `.data.status.toLowerCase() == 'active')`
5. Save file
6. Restart Proxmox e.g.  

        systemctl restart pveproxy.service

