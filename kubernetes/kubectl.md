# kubectl commands

**Basic:**
```
kubectl version --short
```
```
kubectl explain <resource_name>
```
```
kubectl config view
```
```
kubectl cluster-info
```


**Context:**
```
kubectl config current-context
```
```
kubectl config use-context <context_name>
```
```
kubectl config get-contexts
```


**Get:**
```
kubectl get all
```


**Namespace:**
```
kubectl get ns
```
```
kubectl create ns <ns_name>
```
+ --all-namespaces

**Service Account:**
```
kubectl get sa
```


**Node:**
```
kubectl get nodes
```


**Deployment:**
```
kubectl get deployments
```
```
kubectl apply -f <file>.yaml
```
```
kubectl create deployment <deployment_name> --image=<image_name>
```
```
kubectl create deployment <deployment_name> --image=<image_name> --dry-run=client -o yaml
```
```
kubectl describe deployments <deployment_name>
```


**Pod:**
```
kubectl get pods
```
```
kubectl get pod -o wide
```
```
kubectl get pods --show-labels
```
```
kubectl get pods <pod_name> -o jsonpath='{.spec.containers[*].name}'
```
```
kubectl exec -it <pod_name> -- /bin/bash
```
```
kubectl exec -it <pod_name> -c <container_name> -- /bin/bash
```
```
kubectl delete pods <pod_name>
```
```
kubectl describe pods <pod_name>
```
```
kubectl logs <pod_name> -c <container_name>
```


**ReplicaSet:**
```
kubectl get rs
```


**Service:**
```
kubectl get services
```
```
kubectl describe services <service_name>
```


**ConfigMap:**
```
kubectl get configmaps
```


**Secret:**
```
kubectl get secrets
```



