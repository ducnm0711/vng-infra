helm -n ingress-nginx install ingress-nginx ./ingress-nginx-3.35.0/ -f values.yaml

helm -n ingress-nginx diff upgrade ingress-nginx ./ingress-nginx-3.35.0/ -f values.yaml