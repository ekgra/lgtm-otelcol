# Ports Inventory (Grafana, Tempo, OpenTelemetry Collector, Mimir)

Grouped by port and protocol. Rows list both Service and Container usage where applicable.

| Port | Protocol | App      | Component            | Purpose |
|------|----------|----------|----------------------|---------|
| 80   | TCP      | Grafana  | Service              | External HTTP to Grafana (targets 3000) |
| 3000 | TCP      | Grafana  | Container            | Grafana HTTP UI/API |
| 9094 | TCP      | Grafana  | Container            | Gossip/cluster communications (TCP) |
| 9094 | UDP      | Grafana  | Container            | Gossip/cluster communications (UDP) |
| 9000 | TCP      | MinIO    | Service, Container   | S3 API endpoint |
| 9001 | TCP      | MinIO    | Service, Container   | MinIO Console UI |
| 7946 | TCP      | Mimir    | Distributor          | Memberlist gossip (cluster membership) |
| 7946 | TCP      | Mimir    | Ingester             | Memberlist gossip (cluster membership) |
| 7946 | TCP      | Mimir    | Store-gateway        | Memberlist gossip (cluster membership) |
| 8080 | TCP      | Mimir    | Distributor          | HTTP metrics, admin, OTLP HTTP (/otlp), readiness (/ready) |
| 8080 | TCP      | Mimir    | Ingester             | HTTP metrics/admin, readiness |
| 8080 | TCP      | Mimir    | Querier              | HTTP metrics/admin, readiness |
| 8080 | TCP      | Mimir    | Query-frontend       | HTTP metrics/admin, readiness, Prometheus HTTP proxy (/prometheus) |
| 8080 | TCP      | Mimir    | Store-gateway        | HTTP metrics/admin, readiness |
| 9095 | TCP      | Mimir    | Distributor          | gRPC API (write/read internal) |
| 9095 | TCP      | Mimir    | Ingester             | gRPC API (write/read internal) |
| 9095 | TCP      | Mimir    | Querier              | gRPC API (internal) |
| 9095 | TCP      | Mimir    | Query-frontend       | gRPC API (frontend/worker) |
| 9095 | TCP      | Mimir    | Store-gateway        | gRPC API (internal) |
| 3200 | TCP      | Tempo    | Distributor, Ingester, Querier, Query-frontend (Services) | Tempo HTTP API/metrics |
| 4317 | TCP      | Tempo    | Distributor (Service) | OTLP gRPC ingest |
| 4318 | TCP      | Tempo    | Distributor (Service) | OTLP HTTP ingest |
| 55680| TCP      | Tempo    | Distributor (Service) | Legacy OTLP gRPC (deprecated) |
| 7946 | TCP      | Tempo    | Gossip-ring Service   | Memberlist gossip |
| 9095 | TCP      | Tempo    | Ingester/Querier/QF (Services) | gRPC API |
| 9096 | TCP      | Tempo    | Query-frontend (Service) | gRPC load-balancer port |
| 6831 | UDP      | Otelcol  | Service, Container   | Jaeger Thrift Compact ingest |
| 14250| TCP      | Otelcol  | Service, Container   | Jaeger gRPC ingest |
| 14268| TCP      | Otelcol  | Service, Container   | Jaeger Thrift HTTP ingest |
| 4317 | TCP      | Otelcol  | Service, Container   | OTLP gRPC ingest |
| 4318 | TCP      | Otelcol  | Service, Container   | OTLP HTTP ingest |
| 9411 | TCP      | Otelcol  | Service, Container   | Zipkin HTTP ingest |
| 13133| TCP      | Otelcol  | Container            | Collector health_check (liveness/readiness) |
| 3100 | TCP      | Loki     | Distributor Service  | HTTP metrics/API, readiness |
| 9095 | TCP      | Loki     | Distributor Service  | gRPC internal API |
| 3100 | TCP      | Loki     | Distributor Container| HTTP metrics/API |
| 9095 | TCP      | Loki     | Distributor Container| gRPC internal API |
| 7946 | TCP      | Loki     | Distributor Container| Memberlist gossip |
| 3100 | TCP      | Loki     | Ingester Service     | HTTP metrics/API, readiness |
| 9095 | TCP      | Loki     | Ingester Service     | gRPC internal API |
| 3100 | TCP      | Loki     | Ingester Container   | HTTP metrics/API |
| 9095 | TCP      | Loki     | Ingester Container   | gRPC internal API |
| 7946 | TCP      | Loki     | Ingester Container   | Memberlist gossip |
| 3100 | TCP      | Loki     | Querier Service      | HTTP metrics/API, readiness |
| 9095 | TCP      | Loki     | Querier Service      | gRPC internal API |
| 3100 | TCP      | Loki     | Querier Container    | HTTP metrics/API |
| 9095 | TCP      | Loki     | Querier Container    | gRPC internal API |
| 7946 | TCP      | Loki     | Querier Container    | Memberlist gossip |
| 3100 | TCP      | Loki     | Query-frontend Svc   | HTTP frontend (query/tail), metrics |
| 9095 | TCP      | Loki     | Query-frontend Svc   | gRPC frontend |
| 9096 | TCP      | Loki     | Query-frontend Svc   | gRPC load-balancer (grpclb) |
| 3100 | TCP      | Loki     | Query-frontend Ctr   | HTTP frontend/metrics |
| 9095 | TCP      | Loki     | Query-frontend Ctr   | gRPC frontend |
| 7946 | TCP      | Loki     | Query-frontend Ctr   | Memberlist gossip |
| 3100 | TCP      | Loki     | Query-scheduler Svc  | HTTP metrics/admin |
| 9095 | TCP      | Loki     | Query-scheduler Svc  | gRPC (scheduler) |
| 3100 | TCP      | Loki     | Query-scheduler Ctr  | HTTP metrics/admin |
| 9095 | TCP      | Loki     | Query-scheduler Ctr  | gRPC (scheduler) |
| 7946 | TCP      | Loki     | Query-scheduler Ctr  | Memberlist gossip |
| 3100 | TCP      | Loki     | Index-gateway Svc    | HTTP metrics/API |
| 9095 | TCP      | Loki     | Index-gateway Svc    | gRPC internal API |
| 3100 | TCP      | Loki     | Index-gateway Ctr    | HTTP metrics/API |
| 9095 | TCP      | Loki     | Index-gateway Ctr    | gRPC internal API |
| 7946 | TCP      | Loki     | Index-gateway Ctr    | Memberlist gossip |
| 3100 | TCP      | Loki     | Compactor Svc        | HTTP metrics/API |
| 9095 | TCP      | Loki     | Compactor Svc        | gRPC internal API |
| 3100 | TCP      | Loki     | Compactor Ctr        | HTTP metrics/API |
| 9095 | TCP      | Loki     | Compactor Ctr        | gRPC internal API |
| 7946 | TCP      | Loki     | Compactor Ctr        | Memberlist gossip |
| 7946 | TCP      | Loki     | Memberlist Service   | Memberlist gossip (targetPort http-memberlist) |

Notes
- Mimir Services typically expose two ports per component: `8080/TCP` (HTTP) and `9095/TCP` (gRPC). Components participating in memberlist also expose `7946/TCP`.
- Native OTLP to Mimir uses `POST /otlp/v1/metrics` on the Distributor’s HTTP port (8080). Prometheus remote_write uses `POST /api/v1/push` on the same HTTP port.
- Tempo Services commonly expose `3200/TCP` (HTTP), `9095/TCP` (gRPC), and for the query-frontend also `9096/TCP` (gRPC LB). OTLP ingest is on the distributor (`4317/4318`).
- Grafana Service publishes `80/TCP` and targets container `3000/TCP` by default.
- Otelcol Service exposes common ingest ports; the Collector’s own Prometheus metrics are served on `8888/TCP` (scraped internally and not usually exposed via Service).

Unique Ports Mentioned
- 80
- 3000
- 6831
- 8888
- 9000
- 9001
- 9094 (TCP/UDP)
- 9095
- 9096
- 9411
- 13133
- 14250
- 14268
- 3100
- 3200
- 4317
- 4318
- 55680
- 7946
- 8080
