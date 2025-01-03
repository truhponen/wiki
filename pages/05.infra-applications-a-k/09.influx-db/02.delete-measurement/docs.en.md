---
title: 'Delete measurement'
taxonomy:
    category:
        - docs
child_type: docs
routes: {  }
---

To remove measurements, for example, sun rise events that were created due to restart of home assistant, run this in influxDB container.

This is for UTC+2 time zone

    influx delete --bucket homeassistant --start '2024-03-22T10:18:00+02:00' --stop '2024-03-22T10:20:00+02:00' --predicate '_measurement="sensor.aurinko_state"'

This is for UTC time zone - "Z" standing for "Zero time timezone".

    influx delete --bucket homeassistant --start '2024-03-17T08:00:00Z' --stop '2024-03-17T09:00:00Z' --predicate '_measurement="sensor.aurinko_state"'

https://docs.influxdata.com/influxdb/v2/write-data/delete-data/#delete-data-using-the-influx-cli