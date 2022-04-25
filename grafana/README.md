# MONITORING STACK - Grafana

## Installing the Chart

To install the chart with the release name `metrics-grafana`:

```console
sops -d grafana-secrets.yaml | kubectl -n monitor apply -f -
# used to filter dashboards folder during checkout
kubectl -n monitor create configmap git-sync-sparsecheckout --from-file=.sparsecheckout=./.sparsecheckout
helm -n monitor install grafana grafana/grafana -f ./values.yaml --version 6.26.5
```

> **Tip**: List all releases using `helm ls`

## Upgrading the Chart

To upgrade the chart with the release name `metrics-grafana`:

```console
# Preview changes
helm -n monitor diff upgrade grafana grafana/grafana -f ./values.yaml --version 6.26.5

# Upgrade
helm -n monitor upgrade grafana grafana/grafana -f ./values.yaml --version 6.26.5
```
