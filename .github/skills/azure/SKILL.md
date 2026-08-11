---
name: azure
description: 'Design and deploy workloads on Azure with governance, networking, identity, and resource planning. Use when you need Azure hosting, PaaS services, monitoring, networking, or secure cloud architecture guidance.'
argument-hint: 'Describe the workload, required Azure services, region, environment, and deployment objective.'
user-invocable: true
disable-model-invocation: false
---

# Azure Architecture and Deployment Guidance

## When to Use
- The solution needs Azure hosting or managed platform services.
- You need architecture guidance for app hosting, database, networking, or monitoring.
- The project should align with secure cloud deployment standards and lifecycle management.

## Core Principles
- Prefer managed services over custom infrastructure where possible.
- Build with security, identity, and least-privilege access in mind.
- Keep resource naming, tagging, and region strategy consistent.
- Design for cost visibility, observability, and operational resilience.

## Procedure
### 1. Define the workload on Azure
- Choose the correct Azure hosting model: App Service, Azure Container Apps, AKS, Functions, or VM-based services.
- Map dependencies such as database, cache, monitoring, networking, and identity.
- Identify the environment and availability requirements.

### 2. Design the secure architecture
- Use managed identities, RBAC, and network controls where possible.
- Keep public exposure limited to required endpoints.
- Plan for key vaults, secrets, and environment isolation.

### 3. Prepare deployment strategy
- Decide whether the solution should be provisioned by ARM/Bicep, Terraform, or Azure-native tooling.
- Set resource group, subscription, tagging, and environment boundaries.
- Validate cost, scaling, and redundancy expectations.

### 4. Validate before release
- Check that networking, identity, and configuration are aligned with production requirements.
- Run smoke validation on deployed services.
- Confirm monitoring and alerting routes are active.

## Quality Checklist
- Azure architecture fits the workload and scale assumptions.
- Security and identity are handled using managed controls.
- Resources are named and tagged for governance and operations.
- Monitoring and incident response are planned.
- Deployment can be repeated in a predictable manner.

## Example Prompts
- "Design an Azure architecture for a .NET API and PostgreSQL database."
- "Recommend Azure services for a secure multi-service application with monitoring and ingress."
- "Review this Azure deployment for security, cost, and operational readiness."

## Output Expectations
- Azure service selection and deployment model guidance
- secure cloud architecture recommendations
- operating and monitoring alignment for production workloads
