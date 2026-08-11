---
mode: agent
description: "Use when: implementing a system architecture defined in .specs/ARCHITECTURE.md by creating the required services, app structure, and Kubernetes manifests to run the full solution together."
---

## Task

- Implement the architecture described in `.specs/ARCHITECTURE.md` and generate the full working system in this repository.

## Instructions

1. Read `.specs/ARCHITECTURE.md` first and extract:
   - business domains and service boundaries
   - required APIs, apps, and data stores
   - integration patterns and communication flow
   - non-functional requirements and deployment constraints
   - environment variables, ports, and dependencies

2. Create the application architecture in the repository root:
   - create one directory per service
   - keep shared configuration at the root level
   - place deployment manifests and orchestration files at the root, not inside individual services

3. Implement the required services:
   - use the preferred stack described by the repo conventions unless the architecture file explicitly requires a different technology
   - prefer .NET for backend APIs when applicable
   - prefer React or Angular for frontend apps when applicable
   - use PostgreSQL, RabbitMQ, Redis, or other infrastructure components when the architecture requires them
   - ensure each service has a clear responsibility and communicates through the correct interfaces

4. Add orchestration and environment setup:
   - create Dockerfiles for each service when required
   - create a root-level Docker Compose file for local orchestration when useful
   - create Kubernetes manifests under a `kubernetes/` or `k8s/` folder
   - define resources such as `Deployment`, `Service`, `ConfigMap`, `Secret`, and `Ingress` where appropriate
   - make it possible to bring the full system up and down together with simple commands

5. Validate the implementation:
   - check that services can be started in a coherent order
   - ensure configuration, ports, environment variables, and dependencies are consistent across the system
   - confirm the generated Kubernetes manifests support the desired architecture

### Agents Delegation

- Delegate services creation to `backend-developer` agent;
- Delegate frontend application creation to `frontend-developer` agent;
- Delegate containerization and Kubernetes manifests creation, ci/cd pipeline setup, and infrastructure as code files (terraform to up infrastructure resources in `azure`) to `devops` agent;

### Projects/Services Creation Guidelines

- Create one directory per service or application;
- Keep shared configuration at the root level;
- Place deployment manifests and orchestration files at the root, not inside individual services;
- If the technology stack is specified in the architecture file, use it; otherwise, use the preferred stack described in agents guidelines;
- Create a Dockerfile for each service when required;
- Create a root-level Docker Compose file for local orchestration when useful;

### Folder Structure Example

```text
.github/
.specs/
service-api-gateway/
service-order/
service-user/
service-web/
infra/
Dockerfile
docker-compose.yml
kubernetes/
  namespace.yaml
  api-gateway-deployment.yaml
  order-deployment.yaml
  user-deployment.yaml
  web-deployment.yaml
  db-deployment.yaml
  rabbitmq-deployment.yaml
README.md
.gitignore
```

### Kubernetes Guidelines

Create Kubernetes configuration files that support the complete stack:

- namespace and resource names aligned with the architecture
- deployment manifests for all services and supporting infrastructure
- service definitions for internal and external access
- environment configuration via ConfigMaps and Secrets
- volume or database configuration when needed
- basic networking so all services can communicate through the intended topology
- commands or instructions to apply and delete the whole stack

Include a simple deployment workflow in the documentation, such as:

```bash
kubectl apply -f kubernetes/
kubectl delete -f kubernetes/
```

## Output expectations

The result should be a working implementation rather than a partial plan. Create the files needed to satisfy the architecture, not just the design notes.

## Success criteria

The prompt is successful when:

- `.specs/ARCHITECTURE.md` has been read and used as the source of truth
- all main services described by the architecture exist
- service interactions match the architecture
- local and/or containerized execution is possible
- Kubernetes manifests exist to start and stop the full stack together
- README or setup documentation explains how to run the system
