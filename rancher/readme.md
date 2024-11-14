# Deploy Rancher

## Create namespace
The resources created by the Chart should be installed. This should always be cattle-system:
```
kubectl create namespace cattle-system
```
### Deploy Rancher
```
kubectl apply -f rancher.yaml
```

