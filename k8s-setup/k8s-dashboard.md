# Dashboard Setup

- Deploy Dashboard UI

```bash
kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.0.0/aio/deploy/recommended.yaml
kubectl proxy --address 10.0.2.15 --port 8001 --accept-hosts=".*"
```

- Dashboard Url:

http://localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/

- Dashboard Authentication

```bash
kubectl create serviceaccount dashboard-admin-sa

kubectl create clusterrolebinding dashboard-admin-sa --clusterrole=cluster-admin --serviceaccount=default:dashboard-admin-sa

kubectl get secrets
```

- Get the token

```bash
kubectl describe secret <secret-name>
```

