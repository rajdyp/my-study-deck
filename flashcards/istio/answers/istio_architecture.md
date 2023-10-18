![image](https://github.com/rajdyp/rajdyp.github.io/assets/15313631/97cb70e7-b945-42ac-a861-1d690342d904)

istio-proxy
- Run as sidecar
- Handles all incoming and outgoing traffic for the service

Mixer
- Enforce access control and policy check
- Gather metrics (telemetry data) from different components

Galley
- Configuration validation, ingestion, processing and distribution

Pilot
- Configures Envoy proxies
- Maintains a centralized configuration
- Provides service discovery
- Traffic management (e.g., A/B tests, canary rollouts, etc.)
- Resiliency (timeouts, retries, circuit breakers, etc.)

Citadel
- Automated key and TLS certificate management for service-to-service authentication
