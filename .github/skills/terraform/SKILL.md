---
name: terraform
description: 'Design and manage infrastructure as code with Terraform for Azure, cloud networking, and environment provisioning. Use when you need repeatable infrastructure, resource provisioning, state management, and environment consistency.'
argument-hint: 'Describe the infrastructure target, required Azure resources, environment, and whether you need base provisioning or modular reusable templates.'
user-invocable: true
disable-model-invocation: false
---

# Terraform Infrastructure as Code

## When to Use
- You need to provision infrastructure in a repeatable, reviewable way.
- The project uses Azure or other cloud providers and needs environment consistency.
- You want to manage infrastructure through version-controlled templates instead of manual actions.

## Core Principles
- Treat infrastructure as code and keep it in version control.
- Prefer small, reusable modules over one large monolith.
- Keep state secure and environment-specific.
- Validate changes before applying to production environments.
- Design for predictable, repeatable deployments and easy rollback.

## Procedure
### 1. Define the target environment
- Identify the app, networking, identity, and resource requirements.
- Separate development, test, and production environments by configuration or workspaces.
- Capture the minimum required resources and dependencies.

### 2. Structure the code
- Use modules for common patterns such as networking, compute, databases, and monitoring.
- Keep resource naming consistent and environment-aware.
- Use variables, locals, and outputs to keep configuration readable and reusable.

### 3. Secure the deployment
- Store state securely and restrict access to it.
- Avoid embedding secrets in code or state files.
- Use managed identities or secure authentication where available.
- Apply least-privilege access to provider credentials and resources.

### 4. Validate and plan
- Run formatting, validation, and plan steps before applying changes.
- Review diffs carefully for unintended infrastructure drift.
- Check dependencies, lifecycle rules, and outputs before rollout.

### 5. Apply and maintain
- Use safe rollout patterns for production changes.
- Document assumptions, recovery steps, and environment dependencies.
- Review drift or unexpected changes regularly.

## Quality Checklist
- Modules are reusable and maintainable.
- Resource definitions match the platform architecture.
- Secrets and state are handled securely.
- Environment separation is clear and intentional.
- Changes are validated before apply.

## Example Prompts
- "Create Terraform for an Azure resource group with a PostgreSQL database and app service."
- "Structure a reusable Terraform module for Kubernetes networking and ingress."
- "Review this Terraform plan for security, naming, and production-readiness issues."

## Output Expectations
- infrastructure design and resource mapping
- Terraform modules and variable strategy
- secure deployment and state-management guidance
