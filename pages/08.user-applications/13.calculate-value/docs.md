---
title: 'Calculate value'
taxonomy:
    category:
        - docs
child_type: docs
routes:
    default: /influx-db
---

# Calculate

    from(bucket: "homeassistant")
      |> range(start: v.timeRangeStart, stop: v.timeRangeStop)
      |> filter(fn: (r) => r["_measurement"] == "sensor.valoautomatiikka_end_brightness")
      |> filter(fn: (r) => r["_field"] == "value")
      |> map(fn: (r) => ({r with _value: r._value / 100.0 * 60.0}))

https://docs.influxdata.com/flux/v0/stdlib/universe/map/#square-the-value-in-each-row