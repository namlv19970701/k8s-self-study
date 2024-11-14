# Deploy Nginx

NGINX requires certificate files (SSL/TLS certificates) when you want to set up HTTPS (secure HTTP) for a website or web application.
## Prerequisite
- ```cert-manager``` chart

## Enable addons ingress in minikube
```
minikube addons enable ingress -p k8s-node
```

## Create namespace for Nginx
```
kubectl create namespace webservers
```

## Apply nginx chart 
```
kubectl apply -f nginx.yaml
```

## Add host to your local machine
Check minikube ip
```minikube ip -p node
```

Add host ```levietnam.local```
```
echo "<minikube_ip> nginx.levietnam.local" | sudo tee -a /etc/hosts > /dev/null
```
