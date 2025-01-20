---
title: 'Editing configuration files'
date: '22:59 31-12-2024'
taxonomy:
    category:
        - docs
routes:
    default: /editing-configuration-files
---

Most of user and [infra applications](/infra-applications) have some type of configuration files.

[Docker](/docker) volumes are mapped to "/configuration-local"-folder, so if there is configuration files available they are this folder. This folder is also configured to [Filestash](/filestash) to provide streamlined access to configurations.

Depending on application, container needs to be restarted after configuration change.