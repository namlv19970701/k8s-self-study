# Deploy cert-manager

Cert-Manager is an open-source Kubernetes add-on designed to automate the management and issuance of SSL/TLS certificates within Kubernetes clusters. It simplifies the process of obtaining, renewing, and managing certificates for services running in a Kubernetes environment.

## Create namespace for cert-manager
```
kubectl create namespace cert-manager
```

## Deploy cert-manager
```
kubectl apply -f cert-manager.yaml
```


