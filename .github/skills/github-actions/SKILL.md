---
name: github-actions
description: 'Create and maintain GitHub Actions workflows for CI/CD, validation, deployment, and automation. Use when you need build pipelines, test automation, pull request checks, or deployment steps in a GitHub-hosted project.'
argument-hint: 'Describe the workflow goal, target environment, build/test commands, and whether you need PR validation or deployment automation.'
user-invocable: true
disable-model-invocation: false
---

# GitHub Actions CI/CD Workflow

## When to Use
- The project needs automated build, test, or deployment pipelines.
- You need validation on pull requests or main branch updates.
- The repository must use GitHub-hosted automation for quality gates and release orchestration.

## Core Principles
- Keep workflows fast, deterministic, and easy to troubleshoot.
- Validate every change with the smallest meaningful pipeline step.
- Build security and secret hygiene into the pipeline from the start.
- Use environment-specific deployments only when they add clear operational value.

## Procedure
### 1. Define the workflow goals
- Decide whether the workflow is for tests, build validation, packaging, or deployment.
- Map the triggers: push, pull_request, workflow_dispatch, tags, or scheduled runs.
- Identify required secrets, artifact paths, and environment variables.

### 2. Build the CI pipeline
- Run install, restore, lint, test, and build commands in a reproducible environment.
- Fail fast on validation issues to reduce wasted time.
- Keep jobs separated by concern when appropriate.

### 3. Add deployment stages
- Only deploy from trusted branches or tags.
- Use environment protections and approvals for production releases.
- Define the rollout steps and rollback path clearly.

### 4. Secure workflow execution
- Store credentials in GitHub secrets or OIDC-based authentication when possible.
- Avoid exposing tokens in logs or workflow files.
- Restrict workflow permissions to the least required privileges.

### 5. Validate and maintain
- Run the pipeline in a test environment before production use.
- Review logs for flaky steps or hidden dependencies.
- Keep pipeline configuration consistent with the repository’s operating model.

## Quality Checklist
- Workflow triggers match the project’s delivery process.
- Build and test steps are reproducible.
- Secrets are managed securely.
- Deployment channels are protected and documented.
- Pipeline failures are easy to diagnose and fix.

## Example Prompts
- "Create a GitHub Actions pipeline for a .NET API with restore, build, and test validation."
- "Add a CI workflow for a frontend app and a production deployment workflow for Azure."
- "Review this workflow for security hardening and deployment safety."

## Output Expectations
- CI/CD workflow design
- validation and deployment stages
- security-oriented pipeline recommendations
