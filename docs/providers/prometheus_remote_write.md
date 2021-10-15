# Prometheus Remote Write

## Exporter

The `prometheus_remote_write` exporter allows to export SLO metrics to [Prometheus](https://prometheus.io) via the remote write API.

```yaml
exporters:
  prometheus_remote_write:
    url: ${PROMETHEUS_REMOTE_WRITE_ENDPOINT} # <https://<prometheus>/api/v1/push
```

Optional fields:
  * `metrics`: List of metrics to export ([see docs](../shared/metrics.md)).
  * `username`: Username for Basic Auth.
  * `password`: Password for Basic Auth.
  * `job`: Name of `RemoteWrite` job. Defaults to `slo-generator`.
  * `ca_file`: File path to a certificate authority used to validate the authenticity of a server certificate.
  * `cert_file`: File path to a certificate used with the private key.
  * `key_file`: File path to a private key used with the certificate.
  * `insecure_skip_verify`: Boolean to skip TLS chain and host verification.

