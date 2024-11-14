# Deploy Rancher

## Create namespace
The resources created by the Chart should be installed. This should always be cattle-system:
```
kubectl create namespace cattle-system
```

Because my minukube has client version is over v1.31.0, I cannot deploy Rancher by kubectl. So I will deploy it by the following command:
```
helm install rancher rancher-stable/rancher   --namespace cattle-system   --set hostname=rancher.levietnam.local   --set ingress.tls.source=nginx --set global.cattle.psp.enabled=false --version 2.9.3 --no-hooks
```

