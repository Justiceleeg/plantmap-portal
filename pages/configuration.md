---
title: Configuration
---

# Configuration

PlantMap is configured through Helm values. Below are the most common configuration options.

## TLS / HTTPS

PlantMap supports three TLS modes:

| Mode | Description |
|------|-------------|
| `auto` | Automatic certificates via cert-manager |
| `manual` | Provide your own TLS secret |
| `selfsigned` | Auto-generated self-signed certificates |

```bash
# Auto (cert-manager)
--set tls.mode=auto --set tls.host=plantmap.example.com

# Manual (existing TLS secret)
--set tls.mode=manual --set tls.secretName=my-tls-secret

# Self-signed
--set tls.mode=selfsigned --set tls.host=plantmap.example.com
```

## Service Type

```bash
# LoadBalancer
--set service.type=LoadBalancer

# NodePort
--set service.type=NodePort --set service.nodePort=30080

# ClusterIP with Ingress
--set service.type=ClusterIP --set ingress.enabled=true
```

## External Database

To use your own PostgreSQL instead of the embedded one:

```bash
--set postgresql.enabled=false \
--set externalPostgresql.host=db.example.com \
--set externalPostgresql.port=5432 \
--set externalPostgresql.username=plantmap \
--set externalPostgresql.password=YOUR_PASSWORD \
--set externalPostgresql.database=plantmap
```

Same pattern for Redis (`redis.enabled=false` + `externalRedis.*`) and MinIO/S3 (`minio.enabled=false` + `externalMinio.*`).

## Application Features

| Value | Description | Default |
|-------|-------------|---------|
| `app.registrationEnabled` | Allow public user signup | `true` |
| `app.grafanaUrl` | Grafana dashboard URL in app header | `""` |
| `grafana.enabled` | Deploy embedded Grafana | `true` |

See the **Helm Chart Reference** in the sidebar for the complete list of configurable values.
