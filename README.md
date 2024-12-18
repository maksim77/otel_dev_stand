# OpenTelemetry Dev Stand
A simple Docker Compose setup that launches pre-configured and integrated services, allowing fully testing interactions with OpenTelemetry:
- OTEL Collector
- Jaeger
- Prometheus
- Grafana

## OTEL Collector
Listens on standard OTLP ports (4317 gRPC, 4318 HTTP) and sends trace data to Jaeger. It also collects metrics and exposes them on port 8889 as a standard Prometheus exporter.

## Jaeger
Accessible on port 16686. Receives traces from the OTEL Collector.

## Prometheus
Accessible on port 9090.
Collects metrics from the following targets:
- OTEL Collector
- Grafana self-monitoring
- Prometheus self-monitoring

## Grafana
Accessible on port 3000.
Login credentials: `admin/grafana`.
The following datasources are connected:
- Jaeger
- Prometheus