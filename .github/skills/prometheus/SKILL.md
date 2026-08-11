---
name: prometheus
description: 'Instrument services and configure Prometheus for metric collection, alerting, and observability. Use when you need application metrics, infrastructure metrics, service monitoring, or PromQL-based alerting for Docker, Kubernetes, or cloud workloads.'
argument-hint: 'Describe the target service, metric types, scrape endpoints, and whether you need alerts, dashboards, or integration with Grafana.'
user-invocable: true
disable-model-invocation: false
---

# Prometheus Monitoring Design

## When to Use
- The application needs metrics to monitor health, throughput, errors, and latency.
- You are building observability for Docker, Kubernetes, or Azure-hosted services.
- You need dashboards or alerts based on time-series metrics.
- The stack already includes Grafana or a monitoring pipeline.

## Core Principles
- Expose metrics at a single, stable endpoint for Prometheus to scrape.
- Prefer standard instrumentation and meaningful metric names.
- Label metrics clearly with service, environment, and workload identity.
- Keep metrics actionable and low-noise.
- Treat alerting as a product of reliable telemetry and clear thresholds.

## Procedure
### 1. Define the telemetry model
- Identify key signals: request count, latency, response codes, CPU, memory, queue depth, and custom business metrics.
- Map each metric to a business or operational intention.
- Keep labels consistent across services and environments.

### 2. Instrument the application
- Expose metrics through standard endpoints or libraries appropriate to the runtime.
- Add counters, gauges, histograms, and summaries only where they provide operational value.
- Avoid emitting high-cardinality labels that create metric explosion.

### 3. Configure scrape targets
- Define targets for API services, infrastructure nodes, and relevant workloads.
- Confirm job names, scrape interval, and endpoint health.
- Validate that endpoints are discoverable and resilient in clustered environments.

### 4. Build alert rules
- Alert on sustained errors, latency spikes, saturation, and service outages.
- Tie alert severity to customer impact and operational ownership.
- Keep thresholds realistic and documented.

### 5. Validate with Grafana or CLI checks
- Confirm metrics appear in Prometheus with expected labels and values.
- Test queries against realistic traffic and failure scenarios.
- Review dashboards and alerts after deployment to catch blind spots.

## Quality Checklist
- Metrics are readable, stable, and low-noise.
- Scrape targets are healthy and discoverable.
- Labels are useful and not excessively high-cardinality.
- Alerts are actionable and tied to real service behavior.
- Monitoring supports incident diagnosis and service ownership.

## Example Prompts
- "Set up Prometheus for a .NET API with request latency, status codes, and error metrics."
- "Design a Prometheus and Grafana setup for a Kubernetes deployment."
- "Review this PromQL query and alert rule for correctness and operational usefulness."

## Output Expectations
- metric strategy and instrumentation guidance
- scrape configuration for services and infrastructure
- alert rules and readiness for Grafana visualization
