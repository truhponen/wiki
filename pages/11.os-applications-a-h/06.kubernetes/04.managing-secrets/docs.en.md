---
title: 'Working with secrets'
date: '18:48 15-02-2025'
taxonomy:
    category:
        - docs
---

Create secret in CLI

     k create secret generic telegraf-mqtt-influxdb-access-token --from-literal=token=66GqMW ... -em1K3O_SXGu4XOXw== -n analytics

This creates generic secret named "telegraf-mqtt-influxdb-access-token" to a-namespace. Secret is in key "token"
