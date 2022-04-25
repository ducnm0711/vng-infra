# MONITORING STACK - Loki-Stack

- Install the chart with release name `logs-loki`:
```console
helm -n monitor install logs-loki grafana/loki-stack -f values.yaml --version 2.6.4
```

- Upgrade the chart:
```console
helm -n monitor diff upgrade logs-loki grafana/loki-stack -f values.yaml --version 2.6.4
helm -n monitor upgrade logs-loki grafana/loki-stack -f values.yaml -f ./values.yaml --version 2.6.4
```