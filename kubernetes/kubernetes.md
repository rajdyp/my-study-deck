# Kubernetes Notes

![Kubernetes architecture](https://github.com/rajdyp/rajdyp.github.io/blob/master/images/kubernetes/k8-architecture.png)

**Master (brain):**
- kube-apiserver
- etcd
- kube-scheduler
- kube-controller-manager
- cloud-controller-manager


**Node:**
- kubelet
- kube-proxy
- cotainer runtime


**Basic deployment config file:**
```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
  labels:  <=
    app: nginx
spec:
  replicas: 3
  selector:  <=
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:  <=
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:1.14.2
        ports:
        - containerPort: 8080  <=
```

**Basic service config file:**
```
apiVersion: v1
kind: Service
metadata:
  name: my-service
spec:
  selector:
    app: nginx  # deployment label is the selector for service
  ports:
    - protocol: TCP
      port: 80
      targetPort: 8080  # deployment app port is the targetPort for service
```
