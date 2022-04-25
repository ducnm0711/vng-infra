# VNG k8s

Infra repo for dev/test system.  
 
## Install metrics-server
```
kubectl apply -f https://github.com/kubernetes-sigs/metrics-server/releases/latest/download/components.yaml
```

## Prerequisites

- [![Helm Version](https://img.shields.io/badge/helm-%3E%3D%203.0.0-blue)](https://github.com/helm/helm/releases)
- [![Helm Version](https://img.shields.io/badge/helm.secrets-%3E%3D%203.8.3-blue)](https://github.com/jkroepke/helm-secrets)
- [![Helm Version](https://img.shields.io/badge/helm.diff-%3E%3D%203.4.2-blue)](https://github.com/databus23/helm-diff)  

> **Note**: Use `helm-diff` plugin to review changes before run `helm upgrade`.
## Helm Charts
This is the configuration for our Monitoring and Logging stack.

We are relying on below community helm charts:
-  [prometheus-community/kube-prometheus-stack](https://github.com/prometheus-community/helm-charts/tree/main/charts/kube-prometheus-stack)
-  [grafana/grafana](https://github.com/grafana/helm-charts/tree/main/charts/grafana)
-  [grafana/loki-stack](https://github.com/grafana/helm-charts/tree/main/charts/loki-stack)

> **Note**: For stability reason, please consult with maintainers first before upgrading the chart as there maybe changes between major versions.  

Secrets are encrypted with Helm Secrets.

## Add charts to repo list
```
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo add bitnami https://charts.bitnami.com/bitnami
helm repo add grafana https://grafana.github.io/helm-charts
helm repo update
kubectl create ns monitor-prod
```