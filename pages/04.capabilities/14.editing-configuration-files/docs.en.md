---
title: 'Editing configuration files'
date: '22:59 31-12-2024'
taxonomy:
    category:
        - docs
routes:
    default: /editing-configuration-files
---

Most of [container applications](/container-applications) have some type of [configuration](/configurations) files.

[Docker](/docker) volumes are mapped to "/configuration-local"-folder, so if there is [configuration](/configurations) files available they are this folder. This folder is also configured to [Filestash](/filestash) to provide streamlined access to configurations.

Depending on [application](/container-applications), container needs to be restarted after [configuration](/configurations) change.