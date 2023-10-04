# Kubernetes

## Kubernetes Architecture
![image](https://github.com/rajdyp/rajdyp.github.io/assets/15313631/e3f10d7b-a2e9-4ee8-a244-272916b2e55d)
![image](https://github.com/rajdyp/rajdyp.github.io/assets/15313631/b101e23b-3863-4d3c-b234-63503663f8d3)

**Master (brain):**
- kube-apiserver
- etcd
- kube-scheduler
- kube-controller-manager
- cloud-controller-manager

**Worker Node:**
- kubelet
- kube-proxy
- cotainer runtime

## Kubernetes Manifest File
- Basic parts of Kubernetes manifest file:
  - **apiVersion** : Kubernetes API version
  - **kind** : Kind of resource (deployment, service, etc.)
  - **metadata** : Data that uniquely identify the resource (name, namespace, labels, annotations, etc.)
  - **spec** : Desired state for the resource. Depends on the kind of resource. 

## Namespaces
- Mechanism for isolating groups of resources within a single cluster (virtual cluster).
- To access service in another namespace.
  - Add namespace name to the service name.
    ```yaml
    apiVersion: v1
    kind: ConfigMap
    metadata:
    name: mongodb-configmap
    data:
    database_url: mongodb-service.database  # service_name.namespace_name
    ```
## Deployment
- Maintains the history of changes applied to itself.
- Enables rollback to previous state.
  - deployment -> replicaset -> pod

## Service
- Abstraction to help expose pods over a network.
- Defines a logical set of endpoints (usually these endpoints are pods) along with a policy about how to make those pods accessible.
  - Service type:
    - **ClusterIP (default)**: Exposes the service on a cluster-internal IP.
    - **NodePort**: Exposes the service on each node's IP at a static port (the NodePort). 
    - **LoadBalancer**: Exposes the service externally using an external load balancer. 
    - **ExternalName**: Maps the service to the contents of the externalName field (DNS name). 

![service](https://github.com/rajdyp/rajdyp.github.io/assets/15313631/17694c65-c8c0-403c-9ba6-7778f86bc0f9)


  - Headless service
    - Cluster IP is not allocated.
    - kube-proxy does not handle these services.
    - No load balancing or proxying done by the Kubernetes for them.
      - --cluster-ip=None

## Ingress
- Exposes HTTP and HTTPS routes from outside the cluster to services within the cluster.
- Traffic routing is controlled by rules defined on the Ingress resource.
- Gives services externally-reachable URLs, load balance traffic, terminate SSL / TLS, and offer name-based virtual hosting.
  - Must have an ingress controller to satisfy an ingress.
  - Paths that do not include an explicit pathType will fail validation. 
  - There are three supported path types:
    - **ImplementationSpecific:** Matching is up to the IngressClass.
    - **Exact:** Matches the URL path exactly and with case sensitivity.
    - **Prefix:** Matches based on a URL path prefix split by /. 

**Basic deployment config file:**
```yaml
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
```yaml
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

## Taints
- Taints allow node to repel a set of pods.

## Node affinity
- Node affinity restricts which nodes Pod can be scheduled on based on node labels. 
