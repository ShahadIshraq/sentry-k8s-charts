# Sentry Kubernetes Helm Charts

This repository contains Helm charts for deploying Sentry and its dependencies on Kubernetes.

## Architecture Overview

A production-ready Sentry deployment consists of several components:

- **Sentry Web and API services**: The core Sentry application
- **PostgreSQL**: Primary database for Sentry
- **Redis**: Used for caching and queueing
- **Kafka**: Message broker for event streaming (using AutoMQ)
- **ClickHouse**: Analytics database for event storage and querying
- **Nginx/Ingress**: For routing external traffic

## Components

This repository includes charts for deploying:

1. PostgreSQL (for primary database)
2. Redis (for caching and queueing)
3. AutoMQ Kafka (for message brokering)
4. ClickHouse (for analytics)
5. Sentry (core application)

## Usage

For detailed instructions on deploying each component, refer to the individual chart documentation in their respective directories.

## Scaling and Monitoring

The charts include configurations for:
- Horizontal Pod Autoscaling
- Resource management
- Monitoring with Prometheus and Grafana
- Logging

## Maintenance

Best practices for maintaining the deployment:
- Regular backups for PostgreSQL and ClickHouse
- Update procedures
- Resource monitoring and alerts
- Secret and certificate rotation

## Resources

For more information, check the resources listed in the implementation plan.
