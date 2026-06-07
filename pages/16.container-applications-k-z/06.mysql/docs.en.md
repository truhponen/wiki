---
title: MySQL
date: '12:57 22-06-2025'
taxonomy:
    category:
        - docs
---

### Open MySQL database "snippetbox" with user "web"

    mysql -D snippetbox -u web -p

### View content of database

    SELECT id, title, expires FROM snippets;