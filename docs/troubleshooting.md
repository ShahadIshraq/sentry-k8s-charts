# DRAFT for Example

# Troubleshooting Guide

This document provides solutions for common issues that might arise when deploying and operating Sentry using these Helm charts.

## Installation Issues

### Chart Dependency Failures

**Problem**: Chart dependencies fail to update or resolve.

**Solution**:
```bash
helm dependency update ./charts/sentry
helm dependency build ./charts/sentry
```

### Connection Refused Errors

**Problem**: Services cannot connect to each other after deployment.

**Solution**: Check that the services are running and the network policies allow communication:

```bash
kubectl get pods
kubectl describe pod <pod-name>
kubectl logs <pod-name>
```

## PostgreSQL Issues

### Database Connection Errors

**Problem**: Sentry cannot connect to PostgreSQL.

**Solution**: Check PostgreSQL pod status and logs:

```bash
kubectl get pods -l app.kubernetes.io/name=postgresql
kubectl logs <postgresql-pod-name>
```

Verify credentials and connection parameters in Sentry's configuration.

## Redis Issues

### Redis Connection Errors

**Problem**: Sentry cannot connect to Redis.

**Solution**: Check Redis pod status and logs:

```bash
kubectl get pods -l app.kubernetes.io/name=redis
kubectl logs <redis-pod-name>
```

## Kafka (AutoMQ) Issues

### Kafka Connection Errors

**Problem**: Sentry cannot connect to Kafka.

**Solution**: Check Kafka pod status and logs:

```bash
kubectl get pods -l app.kubernetes.io/name=automq-kafka
kubectl logs <kafka-pod-name>
```

Verify S3 bucket configuration if applicable.

## ClickHouse Issues

### ClickHouse Connection Errors

**Problem**: Sentry cannot connect to ClickHouse.

**Solution**: Check ClickHouse pod status and logs:

```bash
kubectl get pods -l app.kubernetes.io/name=clickhouse
kubectl logs <clickhouse-pod-name>
```

## Sentry Issues

### Sentry Web UI Not Loading

**Problem**: The Sentry web interface isn't accessible.

**Solution**: Check the ingress configuration and Sentry web service:

```bash
kubectl get ingress
kubectl get svc
kubectl logs <sentry-web-pod-name>
```

### Migrations Failed

**Problem**: Sentry database migrations fail.

**Solution**: Check migration logs and ensure PostgreSQL is properly initialized:

```bash
kubectl logs <sentry-migrations-pod-name>
```

## Scaling Issues

### Pods Not Scaling

**Problem**: HPA is configured but pods aren't scaling.

**Solution**: Check HPA status and metrics:

```bash
kubectl get hpa
kubectl describe hpa <hpa-name>
```

Ensure metrics server is deployed in your cluster.

## Resource Issues

### Out of Memory Errors

**Problem**: Pods are being OOMKilled.

**Solution**: Increase memory limits in values.yaml:

```yaml
resources:
  limits:
    memory: 4Gi
```

## Performance Tuning

### ClickHouse Performance

**Problem**: ClickHouse queries are slow.

**Solution**: Adjust ClickHouse settings:

```yaml
settings:
  profiles:
    default:
      max_memory_usage: 16000000000
      max_threads: 16
```

### Kafka Performance

**Problem**: Event ingestion is slow.

**Solution**: Increase Kafka resources and partition count:

```yaml
resources:
  limits:
    cpu: 2000m
    memory: 4Gi
```
