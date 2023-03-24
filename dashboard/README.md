## Deploy
kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.7.0/aio/deploy/recommended.yaml

## Proxy
kubectl proxy --address 0.0.0.0 --accept-hosts '.*'
kubectl proxy --address 0.0.0.0 --accept-hosts '.*' >/dev/null 2>&1 &

## Access
https://dash-k8s.lrsoft.id/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/

## Account
kubectl apply -f sa.yaml
kubectl apply -f crb.yaml

## Token
kubectl -n kubernetes-dashboard create token admin-user
