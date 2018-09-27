# Kubernetes - Prometheus
Configuration to setup Kubernetes cluster monitoring using Prometheus

## Creation of Namespace
kubectl create namespace monitoring
## Assigning Read permissions to namespace to fetch metrics. 
kubectl create -f clusterRole.yaml 
## Config map to dynamic discovery of pod/service etc. 
kubectl create -f config-map.yaml -n monitoring 
## Create Deployment 
kubectl create  -f prometheus-deployment.yaml -n monitoring 
## Expose PMT Service.
kubectl create -f prometheus-service.yaml -n monitoring
