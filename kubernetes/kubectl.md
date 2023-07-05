# kubectl commands

## Basic
```yaml
kubectl version --short
```
```yaml
kubectl explain <resource_name>
```
```yaml
kubectl config view
```
```yaml
kubectl cluster-info
```


## Context
```yaml
kubectl config current-context
```
```yaml
kubectl config use-context <context_name>
```
```yaml
kubectl config get-contexts
```


## Get
```yaml
kubectl get all
```


## Namespace
```yaml
kubectl get ns
```
```yaml
kubectl create ns <ns_name>
```
```yaml
kubectl api-resources --namespaced=true
```
```yaml
kubectl api-resources --namespaced=false
```
+ --all-namespaces


## Service Account
```yaml
kubectl get sa
```


## Node
```yaml
kubectl get nodes
```


## Deployment
```yaml
kubectl get deployments
```
```yaml
kubectl apply -f <file>.yaml
```
```yaml
kubectl create deployment <deployment_name> --image=<image_name>
```
```yaml
kubectl create deployment <deployment_name> --image=<image_name> --dry-run=client -o yaml
```
```yaml
kubectl describe deployments <deployment_name>
```


## Pod
```yaml
kubectl get pods
```
```yaml
kubectl get pod -o wide
```
```yaml
kubectl get pods --show-labels
```
```yaml
kubectl get pods <pod_name> -o jsonpath='{.spec.containers[*].name}'
```
```yaml
kubectl exec -it <pod_name> -- /bin/bash
```
```yaml
kubectl exec -it <pod_name> -c <container_name> -- /bin/bash
```
```yaml
kubectl delete pods <pod_name>
```
```yaml
kubectl describe pods <pod_name>
```
```yaml
kubectl logs <pod_name> -c <container_name>
```


## ReplicaSet
```yaml
kubectl get rs
```


## Service
```yaml
kubectl get services
```
```yaml
kubectl describe services <service_name>
```


## ConfigMap
```yaml
kubectl get configmaps
```


## Secret
```yaml
kubectl get secrets
```

## 
```yaml
kubectl get mutatingwebhookconfigurations.admissionregistration.k8s.io 
```

