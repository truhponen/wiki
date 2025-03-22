---
title: Setup
date: '20:38 15-03-2025'
taxonomy:
    category:
        - docs
---

### Prepare git and github

1. Create SSH key

        ssh-keygen -t ed25519 -C "your@email.com"
    
    Save with default name - it saves a lot

2. Add public key to Github

3. Clone repo

        git clone git@github.com:truhponen/home.git

4. Add your email

        git config --global user.email "your@email.com"

5. Add your name

        git config --global user.name "First Last-name"

### Prepare Git-secret

1. Create GPG key

        gpg --gen-key

2. Initialize

        git secret init

3. Tell who you are

        git secret tell your@email.com

    Use same email as in GPG