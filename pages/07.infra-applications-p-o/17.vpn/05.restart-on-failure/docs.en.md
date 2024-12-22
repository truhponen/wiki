---
title: 'Restart on failure'
date: '20:44 22-12-2024'
taxonomy:
    category:
        - docs
---

If Raspberry Pi, OS has to be Ubuntu 20.04 LTS.

Instructions: https://openvpn.net/vpn-server-resources/install-openvpn-access-server-on-raspberry-pi/

Status of Access Server

    sudo systemctl status openvpnas

Update host's privkey to OpenVPS

    sudo /usr/local/openvpn_as/scripts/sacli --key "cs.priv_key" --value_file "/etc/letsencrypt/live/truhponen.duckdns.org/privkey.pem" ConfigPut

Update host's fullchain to OpenVPS

    sudo /usr/local/openvpn_as/scripts/sacli --key "cs.cert" --value_file "/etc/letsencrypt/live/truhponen.duckdns.org/fullchain.pem" ConfigPut

Restart Access Server

    sudo /usr/local/openvpn_as/scripts/sacli start

OR
    
    sudo systemctl restart openvpnas