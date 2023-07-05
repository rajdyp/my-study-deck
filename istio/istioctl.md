# Istio commands

```
istioctl version
```

```
istioctl x precheck
```

## Enable automatic sidecar injection

```
kubectl label namespace default istio-injection=enabled
```
```
kubectl get ns -Listio-injection
```
