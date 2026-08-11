---
agent: orchestrator
description: This prompt is used to develop new software features based on specs inside .specs/backlog folder. The idea is to check for specs in .specs/backlog folder in root one, and then build them using the appropriate agents, and finally move the spec to .specs/done folder after the implementation is done.
---

# Build Pending Specs

- This prompt is used in order to develop new software features based on specs inside .specs/backlog folder.
- The idea is to check for specs in .specs/backlog folder in root one, and then build them using the appropriate agents, and finally move the spec to .specs/done folder after the implementation is done.

## Instructions

1. Search for specs in .specs/backlog folder in root one.
  - The spec file must be in markdown format and have a .spec.md extension (except for the template.spec.md, that is the template one).
  - The spec file must have a title, description, acceptance criteria, diagrams, and notes/assumptions sections.
2. For each spec found:
  - Read the spec and reason about the implementation.
  - Identify which agents are necessary to implement the spec.
      - Use the `backend-developer` agent to write and implement services with business logic that satisfies the requirement spec.
      - Use the `frontend-developer` agent to implement UI components and interactions that satisfy the requirement spec.
      - Use the `ui-designer` agent to design UI components and layouts if a frontend application is involved.
  - Break down the spec into smaller tasks and assign them to the appropriate agents.
  - Create a new branch in order to build the spec. Name it as feat/<spec-name> where <spec-name> is a descriptive name of the spec.
  - Create/modified necessary services files and implement the spec using the appropriate agents.
  - After the spec is implemented, create a pull request to develop with a clear description of the changes made and how they satisfy the spec.
  - Alongside, move the spec file from .specs/backlog to .specs/done and add a note about the implementation in the spec file.

### Services disposition

- Create services application in root folder.
- Create one folder per service.
- Follow the structure below:
  - .github
  - .specs
  - service-example-api
  - service-example-web
  - service-example-app
  - (put any config files as docker-compose.yml, kubernetes config file, ci/cd config files, and everything that going to be used for the services altogher in the root folder, and not inside the service folders)
  - README.md
  - .gitignore

### Technology stack

- Use `angular` or `react` for frontend applications. Use `angular` for more complex applications, enterprise ones. And use `react` for simpler applications, MVPs, and prototypes.
- Use `csharp` with .NET LTS version using webapi template for backend services.
- Use `postgresql` as relational database in scenarios where I needed to store structured data, and use `mongodb` as non-relational database in scenarios where I need to store unstructured data.
- Use `kubernetes` for container orchestration and `docker` for containerization.
- Use `grafana` and `prometheus` for monitoring and observability.
- Use `git` for version control and `github` for repository hosting and collaboration.
- Use `github actions` for CI/CD pipelines.
- Use `terraform` for infrastructure as code and `ansible` for configuration management.
- Use `azure` as could provider.

### Distributed System Architecture Approach

- Use `microservices` architecture for complex systems with multiple services that need to be independently deployable and scalable.
- Use `api-gateway` to route requests coming from clients, and send it to a broker, and then the broker will send it to the appropriate service.
- Use `rabbitmq` as message broker for asynchronous communication between services.
- Use `n-tier-architecture` for simpler systems with a clear separation of concerns between presentation, business logic, and data access layers.

## Constraints

- ALWAYS build the specs/requirements following security best practices and principles.
- ALWAYS build specs to accomplish acceptance criteria checklist.
- USE diagrams in spec in order to build business logic and architecture of the system.
