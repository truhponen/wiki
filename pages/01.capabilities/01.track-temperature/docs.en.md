---
title: 'Track temperature'
date: '19:47 21-12-2024'
published: true
taxonomy:
    category:
        - docs
slug: track-temperature
---

Temperature tracking is process that transfers temperature information from sensors to Home Assistant and other applications.

1. Temperature is tracked with [Clas Ohlson's](https://www.clasohlson.com/fi/Lampotila-anturi-kosteusmittari/p/36-6726-1)  and [Suomen Lämpömittari's](https://www.suomenlampomittari.fi/tuotteet/lahetin-mittarille-7410/) weather station sensors which send information with 433 MHz radio.
2. Information sent by sensors is captured with [Lilygo LoRa32 V2.1_1.6](https://lilygo.cc/products/lora3) which runs Open MQTT Gateway
3. Open MQTT Gateway send information by wlan to Mosquitto MQTT server
4. Mosquitto publishes information to Home Assistant and Influx DB
5. Home Assistant stores information to sensors which are displayed on frontend
6. Influx DB uses Telegraf agent to read information to Influx DB