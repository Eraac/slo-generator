# Prometheus Remote Write Exporter

## Exporter

The `prometheus_remote_write` exporter allows to export SLO metrics to any of the compatible [Remote Write](https://prometheus.io/docs/operating/integrations/#remote-endpoints-and-storage) endpoints.

```yaml
exporters:
  prometheus_remote_write:
    url: https://your-cortex-endpoint/api/v1/push
    username: Basic Auth username
    password: basic Auth password
    tls_config:
      ca_file: Path to the PEM file containing the entire CA chain
      ca_cert: Path to the CA certificate file
      ca_key: Path to the CA certificate key file
      insecure_skip_verify: True|False - whether to disable SSL verification entirely
```

Required fields:
  * `url`: Fully-qualified remote write endpoint, including the API path. E.g. `api/v1/push` for Cortex or `api/v1/receive` for Thanos etc.

Optional fields:
  * `metrics`: List of metrics to export ([see docs](../shared/metrics.md))
  * `username`: Username for Basic Auth.
  * `password`: Password for Basic Auth.
  * `tls_config`: Dict holding the custom TLS configuration.
