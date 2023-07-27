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
```yaml
kubectl config set-context
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
```yaml
kubectl get node -o json | jq ".items[] | {name:.metadata.name} + .status.capacity"
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
kubectl describe deployment <deployment_name>
```
```yaml
kubectl scale deployment <deployment_name> --replicaset=2
```
```yaml
kubectl rollout status deployment <deployment_name>
```
```yaml
kubectl rollout undo deployment <deployment_name> --to-revision=<revision_no>
```

## ReplicaSet
```yaml
kubectl get rs
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


## Labels
```yaml
kubectl label pods -l <label=value>
```
```yaml
kubectl label pods -l <label>- 
```

## Service
```yaml
kubectl get services
```
```yaml
kubectl describe service <service_name>
```
```yaml
kubectl expose deployment <deployment_name> --type=LoadBalancer --name=<service_name>
```

## ConfigMap
```yaml
kubectl set env deployment <deployment_name> <key>="<value>"  # without configmap
```
```yaml
kubectl create cm <configmap_name> --from-env-file=/app/test/some.properties
```
```yaml
kubectl get configmaps
```


## Secret
```yaml
kubectl create secret generic <secret_name> --from-literal=username='<user>' --from-literal=password='<password>'
```
```yaml
kubectl get secrets
```

## Logs
```yaml
kubectl logs <resource>
```
```yaml
kubectl logs <resource> -f
```


## 
```yaml
kubectl get mutatingwebhookconfigurations.admissionregistration.k8s.io 
```

