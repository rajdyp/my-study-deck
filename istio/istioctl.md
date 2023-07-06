# Istio commands

```yml
istioctl version
```

```yml
istioctl x precheck
```

```yml
istioctl proxy-status
```

```yml
istioctl install --set profile=<profile>
```

```yml
istioctl manifest generate -f <config>.yaml
```

```yml
istioctl proxy-config endpoints deploy/foo.foo
```

## Enable automatic sidecar injection

```yml
istioctl kube-inject -f <kube_resource>.yaml | less
```

```yml
kubectl label namespace default istio-injection=enabled
```

```yml
kubectl get ns -Listio-injection
```
