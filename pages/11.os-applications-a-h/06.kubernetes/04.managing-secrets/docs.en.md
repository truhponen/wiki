---
title: 'Working with secrets'
date: '18:48 15-02-2025'
taxonomy:
    category:
        - docs
---

#### Create secret in CLI

     k create secret generic telegraf-mqtt-influxdb-access-token --from-literal=token=66GqMW [...] -em1K3O_SXGu4XOXw== -n analytics

This creates generic secret named "telegraf-mqtt-influxdb-access-token" to "analytics"-namespace. Secret is in key "token".


#### View secret

    kubectl get secret telegraf-mqtt-influxdb-access-token -n analytics --output=yaml

```
apiVersion: v1
data:
  token: NjZHcU1XWnFpZGRMRWZvR3R [...] VtMUszT19TWEd1NFhPWHc9PQ==
kind: Secret
metadata:
  creationTimestamp: "2025-02-15T18:43:38Z"
  name: telegraf-mqtt-influxdb-access-token
  namespace: analytics
  resourceVersion: "3228203"
  uid: 6f79cbf5-a791-4cba-949a-ac364871f8a2
type: Opaque
```

#### Using as environmental variable


```
        env:
        - name: INFLUX_TOKEN
          valueFrom:
            secretKeyRef:
              name: telegraf-mqtt-influxdb-access-token
              key: token
```