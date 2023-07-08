
## Traffic Management
- ingress-gateway
  ```yml
  - Yes
  ```
    - virtual service
      ```yml
      - Timeouts
      - Retry policies
      ```
        - destination rules
          ```yml
          - Traffic rules
          - Subsets
          ```

## Discovery Selectors
- By default, Istio control plane watches and processes updates for all Kubernetes resources in a cluster. 
- Discovery selectors allow us to control which namespaces Istio control plane watches and sends configuration updates for.
- We can update the IstioOperator to include the discoverySelectors field as shown below:

```yml
apiVersion: install.istio.io/v1alpha1
kind: IstioOperator
metadata:
  namespace: istio-system
  name: istio-demo
spec:
  meshConfig:
    discoverySelectors:
    - matchLabels:
        env: test
```


