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
4. [Mosquitto](/mosquitto) publishes information to
5. [Home Assistant](/home-assistant) MQTT-integration reads [Mosquitto's](/mosquitto) message queue and stores information to sensors.
   1. [Home Assistant](/home-assistant) diplays sensor's information in frontend
7. [Telegraf](/telegraf) reads [Mosquitto's](/mosquitto) message queue and stores information to [Influx DB's](/influx-db) bucket called "MQTT".
8. [Grafana](/grafana) visualizes Influx DB information. Grafana dashboard in enbedded (iframe) to [Home Assistant](/home-assistant) UI.