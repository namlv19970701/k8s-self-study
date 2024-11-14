# Deploy Nginx

NGINX requires certificate files (SSL/TLS certificates) when you want to set up HTTPS (secure HTTP) for a website or web application.

## Enable addons ingress in minikube
```
minikube addons enable ingress -p k8s-node
```

## Create TLS certificates
```
openssl req -x509 -newkey rsa:4096 -keyout ingress-tls.key -out ingress-tls.crt -days 365 -nodes -subj "/CN=levietnam.local"
```

## Create namespace for Nginx
```
kubectl create namespace web-servers
```

## Create secret on ```web-servers``` namespace
```
kubectl create secret tls ingress-tls --cert=ingress-tls.crt --key=ingress-tls.key -n web-servers
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
echo "<minikube_ip> levietnam.local" | sudo tee -a /etc/hosts > /dev/null
```
