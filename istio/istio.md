
## Traffic Management
- Gateway
  ```yml
  - Ports
  - Protocols
  - Hosts
  ```
    - VirtualService
      ```yml
      - Hosts
      - Route
      - Timeouts
      - Retry policies
      ```
        - DestinationRule
          ```yml
          - Subsets
          - Traffic Policies
            - LB setting
            - Connection pool settings
            - Outlier detection
            - Client TLS settings
            - Port traffic policy
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


