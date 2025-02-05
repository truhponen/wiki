---
title: Sensors
date: '20:44 21-12-2024'
taxonomy:
    category:
        - docs
routes:
    default: /sensors
media_order: ClasOhlsonSensori.png
---

There is different types of sensors

## Sensors with 433 MHz radio

[Temperatures are tracked](/track-temperature) with [Clas Ohlson's](https://www.clasohlson.com/fi/Lampotila-anturi-kosteusmittari/p/36-6726-1)  and [Suomen Lämpömittari's](https://www.suomenlampomittari.fi/tuotteet/lahetin-mittarille-7410/) weather station sensors which send information with 433 MHz radio.

#### Clas Ohlson Sensor

![Clas Ohlson Sensor](ClasOhlsonSensori.png?resize=150 "ClasOhlsonSensori")

#### Suomen Lämpömittari Sensor

![Suomen Lämpömittari Sensor](SuomenLampomittariSensori.jpg?lightbox=1024,resize=400 "SuomenLampomittariSensori")

## Sensors with Zigbee

Zigbee sensors are used to track motion and lightness.

* Some Philips Hue motion sensors are integrated through [Zigbee2MQTT](/zigbee2mqtt)
* Some Philips Hue motion sensors are integrated through [Hue bridge](/hue-bridge)