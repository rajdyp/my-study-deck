# Istio commands

```
istioctl version
```

```
istioctl x precheck
```

```
istioctl proxy-status
```

```
istioctl install --set profile=<profile>
```

## Enable automatic sidecar injection

```
istioctl kube-inject -f <kube_resource>.yaml | less
```

```
kubectl label namespace default istio-injection=enabled
```

```
kubectl get ns -Listio-injection
```
