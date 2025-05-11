# DRAFT for Example

# Sentry K8s Charts

This document provides information about how to use and contribute to this Helm chart repository.

## Using the Charts

### Adding the Repository

```bash
helm repo add sentry-k8s https://REPOSITORY_URL
helm repo update
```

### Installing Charts

```bash
# Install PostgreSQL
helm install postgresql sentry-k8s/postgresql

# Install Redis
helm install redis sentry-k8s/redis

# Install AutoMQ (Kafka)
helm install automq-kafka sentry-k8s/automq-kafka

# Install ClickHouse
helm install clickhouse sentry-k8s/clickhouse

# Install Sentry with all dependencies
helm install sentry sentry-k8s/sentry
```

## Configuration

Each chart includes a default `values.yaml` file with the most common configuration options. For a complete deployment, you should customize these values for your environment.

Example:

```bash
helm install sentry sentry-k8s/sentry -f custom-values.yaml
```

## Chart Development

### Prerequisites

- Helm 3.0+
- Kubernetes 1.19+
- kubectl

### Testing Charts Locally

```bash
# Lint the chart
helm lint charts/sentry

# Test template rendering
helm template charts/sentry

# Install chart locally for testing
helm install sentry-test ./charts/sentry --dry-run
```

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.
