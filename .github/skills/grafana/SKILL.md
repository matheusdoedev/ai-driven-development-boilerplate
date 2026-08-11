---
name: grafana
description: 'Create dashboards, visualize metrics, and monitor application health with Grafana. Use when you need operational dashboards, alerting, metrics exploration, and observability for services running in Docker, Kubernetes, or Azure.'
argument-hint: 'Describe the service, metrics to monitor, deployment target, and whether you need dashboards, alerts, or alert thresholds.'
user-invocable: true
disable-model-invocation: false
---

# Grafana Monitoring and Visualization

## When to Use
- You need a dashboard to visualize application health or infrastructure metrics.
- The stack uses Prometheus, Azure Monitor, or other data sources.
- You need to track latency, saturation, errors, and business KPIs.
- You want alerting, review panels, and operational visibility across services.

## Core Principles
- Start with a clear operational question before building the dashboard.
- Use simple, readable panels that answer the team’s real monitoring needs.
- Prefer actionable metrics over noisy or decorative charts.
- Design dashboards around user impact, service health, and error trends.
- Keep alert thresholds realistic and tied to service-level objectives.

## Procedure
### 1. Define monitoring goals
- Decide what the dashboard should answer: uptime, resource pressure, throughput, failures, latency, or cost.
- Identify the stakeholders: developers, SREs, or product owners.
- Keep the first version focused on the highest-value operational signals.

### 2. Choose data sources
- Connect Grafana to Prometheus, Azure Monitor, Loki, or another supported source.
- Verify that the relevant metrics are exposed by the application and infrastructure.
- Normalize labels and naming so panels are consistent and understandable.

### 3. Build useful panels
- Use latency, error rate, request volume, saturation, and health widgets for core services.
- Add business KPI panels only when they directly support operational decisions.
- Group panels by service, environment, or domain to make navigation easier.

### 4. Add alerting
- Define alerts for sustained failures, saturation, or critical thresholds.
- Notify the right team with actionable alert text.
- Avoid alert fatigue by setting sensible evaluation windows and reasonable severities.

### 5. Validate and refine
- Check that panel values match real application behavior.
- Remove confusing or duplicate metrics.
- Review the dashboard after real traffic or incident scenarios to ensure it supports decisions.

## Quality Checklist
- Dashboard answers a specific operational need.
- Metrics are correctly sourced and labeled.
- Panel names and thresholds are understandable.
- Alerts are actionable and not noisy.
- The dashboard supports incident response and service reviews.

## Example Prompts
- "Create a Grafana dashboard for a .NET API showing latency, error rate, and request volume."
- "Design a Grafana monitoring dashboard for Kubernetes workloads with CPU, memory, and pod health."
- "Review this alert configuration for noisy thresholds and operational clarity."

## Output Expectations
- dashboard layout and panel recommendations
- alert strategy and metric mapping
- observability plan aligned with service health and user impact
