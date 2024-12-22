---
title: 'Enable SSH (with password) to container'
date: '21:08 22-12-2024'
taxonomy:
    category:
        - docs
---

1. Go to host

2. Attach container to host

       lxc-attach --name <ID>

3. Edit SSH-config in container

       nano /etc/ssh/sshd_config

4. Change ...

    `PermitRootLogin without-password`

    to

    `PermitRootLogin yes`

5. Save and restart ssh service

    service ssh restart