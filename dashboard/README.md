## Deploy
kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.7.0/aio/deploy/recommended.yaml

## Proxy
kubectl proxy --port=30080 --address 0.0.0.0 --accept-hosts '.*'
kubectl proxy --port=30080 --address 0.0.0.0 --accept-hosts '.*' >/dev/null 2>&1 &

## Access
https://gb-dash-k8s.lrsoft.id/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/

https://rpi4-dash-k8s.lrsoft.id/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/

## Account
kubectl apply -f sa.yaml
kubectl apply -f crb.yaml

## Token
kubectl -n kubernetes-dashboard create token admin-user
