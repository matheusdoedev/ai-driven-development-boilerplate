---
name: kubernetes
description: 'Design, deploy, secure, and troubleshoot Kubernetes workloads for application services. Use when you need manifests, deployments, services, ingress, secrets, autoscaling, health checks, observability, or container orchestration in Azure or Docker-based environments.'
argument-hint: 'Describe the workload type, expected traffic, required ingress, persistence needs, and target environment (local, Docker Desktop, Azure, or cluster).'
user-invocable: true
disable-model-invocation: false
---

# Kubernetes Workload Design and Delivery

## When to Use
- The system needs container orchestration for service deployment and scaling.
- You need to define Kubernetes manifests for workloads, services, ingress, volumes, or secrets.
- You are shipping a backend, frontend, or multi-service application that should run reliably in a cluster.
- The platform requires health checks, rolling updates, auto-scaling, or observability.
- You need to align the project with the repository standard of Docker plus Kubernetes orchestration.

## Core Principles
- Keep the desired state explicit, versioned, and reviewable.
- Separate runtime configuration from application code.
- Prefer least-privilege access, secure defaults, and minimal surface exposure.
- Design for resilience: health probes, retries, resource limits, and rolling upgrades.
- Make workloads easy to operate, monitor, and troubleshoot in real environments.
- Validate the cluster configuration against real business and security requirements before completion.

## Procedure

### 1. Confirm the workload and runtime model
- Determine whether the service is stateless, stateful, or batch-oriented.
- Identify if the app needs HTTP ingress, internal-only access, background jobs, or event-driven workers.
- Check whether the project uses Docker containers, .NET APIs, web apps, or multi-service composition.
- Define the target environment: local development, test cluster, Azure Kubernetes Service, or another platform.

### 2. Define the deployment architecture
- Create a namespace for logical separation when appropriate.
- Use Deployments for long-running application workloads.
- Use Services to expose traffic internally or externally.
- Use Ingress or LoadBalancer resources when external access is required.
- Add ConfigMaps and Secrets for configuration and credentials.
- Use PersistentVolumeClaims only when state needs durable storage.

### 3. Model application resources cleanly
- Keep manifests focused on one concern per file.
- Follow clear naming conventions and labels for app ownership, tier, and environment.
- Define environment-specific values using overlays, Helm values, or separate manifests.
- Ensure resources are portable and understandable by other developers and operators.

### 4. Hardening and security
- Run workloads as non-root whenever possible.
- Use read-only filesystem settings for immutable workloads when appropriate.
- Avoid embedding secrets directly in manifests; prefer Secret resources and external secret managers.
- Apply Role-Based Access Control with minimal service account permissions.
- Restrict ingress exposure using network policies, proper host rules, and TLS termination.
- Enable secure transport and verify that health checks do not leak sensitive internals.

### 5. Reliability and scaling
- Add liveness and readiness probes to catch unhealthy pods before traffic reaches them.
- Configure resource requests and limits to avoid noisy neighbors and eviction issues.
- Use rolling updates and strategy settings to reduce downtime.
- Add autoscaling for CPU, memory, or custom metrics when expected traffic varies.
- Define failover, restart, and recovery expectations for critical services.

### 6. Observability and operations
- Expose metrics and logs for application and cluster health.
- Standardize health endpoints, container logs, and structured output.
- Use Prometheus, Grafana, or equivalent tooling for monitoring and dashboards.
- Add startup, shutdown, and troubleshooting documentation for operators.
- Make incident response straightforward by naming resources and documenting dependencies.

### 7. Validate before deployment
- Confirm the container image builds and runs correctly.
- Validate that Services and Ingress route requests correctly.
- Check readiness and liveness behavior under realistic startup conditions.
- Verify secrets and config injection work in the chosen environment.
- Confirm resource limits, autoscaling, and persistence behave as expected.

## Decision Guidance

### Use Kubernetes when:
- The system is composed of multiple services or containers.
- The workload needs scaling, self-healing, or rolling updates.
- The platform requires consistent orchestration across development, staging, and production.
- The team wants to align with cloud-native patterns and observability.

### Avoid Kubernetes when:
- The project is a small single-service prototype with no need for orchestration.
- The team is not ready to operate cluster-level debugging and deployment concerns.
- A simpler PaaS or container runtime is enough for the current scope.

## Quality Checklist
Before considering a Kubernetes implementation complete, verify the following:
- Workloads are packaged as container images with clear build paths.
- Deployments, Services, and Ingress rules match the architecture.
- Secrets and config values are not hardcoded in source files.
- Health checks and restart behavior are defined.
- Resource requests and limits are set appropriately.
- Security permissions and access boundaries are limited to the minimum required.
- Monitoring and observability are in place.
- The environment is runnable and documented for deployment and recovery.

## Example Prompts
- "Create a Kubernetes deployment for a .NET API with a Service and Ingress configuration."
- "Design a secure Kubernetes setup for a multi-service application with secrets, ConfigMaps, and autoscaling."
- "Review this manifest for readiness, resource limits, and least-privilege security issues."
- "Set up a local Kubernetes environment for an app using Docker and an internal service mesh pattern."
- "Define a production-ready cluster architecture for a React frontend and API backend on Azure."

## Output Expectations
When used for backlog or engineering work, this skill should produce or validate:
- Kubernetes manifests for workload deployment
- Network exposure and service routing design
- Security and Secret handling recommendations
- Observability and health strategy
- A clear checklist for validation and rollout readiness

## Related Guidance
This skill complements Docker containerization, PostgreSQL persistence, monitoring with Prometheus and Grafana, and Azure-based deployment architecture for service-oriented software.
