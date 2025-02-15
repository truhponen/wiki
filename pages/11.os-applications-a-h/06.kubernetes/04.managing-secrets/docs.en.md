---
title: 'Working with secrets'
date: '18:48 15-02-2025'
taxonomy:
    category:
        - docs
---

#### Create secret in CLI

**Option 1**

     kubectl create secret generic telegraf-mqtt-influxdb-access-token --from-literal=token=66GqMW [...] -em1K3O_SXGu4XOXw== -n analytics

This creates generic secret named "telegraf-mqtt-influxdb-access-token" to "analytics"-namespace. Secret is in key "token".

**Option 2**

    kubectl create secret generic telegraf-mqtt-influxdb-access-token --from-literal=INFLUX_TOKEN=66GqMW [...] -em1K3O_SXGu4XOXw== -n analytics
 
In this version key is name of expected environmental variable "INFLUX_TOKEN".
 

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

**Option 1**

```
        image: docker.io/telegraf:1.33.2
        env:
        - name: INFLUX_TOKEN
          valueFrom:
            secretKeyRef:
              name: telegraf-mqtt-influxdb-access-token
              key: token
```
**Option 2**

```
    image: docker.io/telegraf:1.33.2
    envFrom:
    - secretRef:
        name: telegraf-mqtt-influxdb-access-token
 ```