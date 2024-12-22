---
title: 'Install DNSmasq'
taxonomy:
    category:
        - docs
child_type: docs
routes: {  }
---

1. Update

       apt-get update

2. Install

       apt-get install dnsmasq

3. Edit

       nano /etc/dnsmasq.conf

4. Uncomment additional config file

    `conf-file=/etc/dnsmasq.more.conf`

5. Create additional config file

       nano /etc/dnsmasq.more.conf

6. Add configs

	`domain-needed`
  `local=/koti/`
  `address=/koti/192.168.68.3`

7. Restart DNSmasq

       systemctl restart dnsmasq

8. Check status of DNSmasq

       systemctl status dnsmasq

9. Test

       nslookup tamakin.koti 192.168.68.102