---
title: 'Track temperature'
date: '19:47 21-12-2024'
published: true
taxonomy:
    category:
        - docs
routes:
    default: /track-temperature
---

Temperature tracking is process that transfers [temperature information](/temperature) from [sensors](/sensors) to [Home Assistant](/home-assistant) and other applications.

Temperatures are displayed in [Home Assistant](/home-assistant) UI.

1. [Temperature](/temperature) is tracked with weather station [sensors](/sensors).
2. Information sent by sensors is captured with [433 MHz adapter](/433mhz-adapter) running [Open MQTT Gateway](/open-mqtt-gateway)
3. [Open MQTT Gateway](/open-mqtt-gateway) send information by [wlan](/lan) to [Mosquitto MQTT server](/mosquitto)
4. [Mosquitto](/mosquitto) publishes information to  [Home Assistant](/home-assistant) and [Influx DB](/influx-db)
5. [Home Assistant](/home-assistant) stores information to sensors which are displayed on frontend
6. [Influx DB](/influx-db) uses [Telegraf](/telegraf) agent to read information to [Influx DB](/influx-db)