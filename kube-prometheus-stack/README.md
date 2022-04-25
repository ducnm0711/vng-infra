# MONITORING STACK - Kube-Prometheus-Stack

- Install the chart with release name `metrics-prometheus`:
```console
helm -n monitor install metrics-prometheus prometheus-community/kube-prometheus-stack -f ./values.yaml --version 34.10.0
```

- Upgrade the chart:
```console
helm -n monitor diff upgrade metrics-prometheus prometheus-community/kube-prometheus-stack -f ./values.yaml --version 34.10.0
helm -n monitor upgrade metrics-prometheus prometheus-community/kube-prometheus-stack -f ./values.yaml --version 34.10.0
```