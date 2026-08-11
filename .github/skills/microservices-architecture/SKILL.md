---
name: microservices-architecture
description: "Use when: you need to design or refactor distributed systems into independently deployable services with clear boundaries, contracts, and operational concerns."
argument-hint: "Describe the business domain, service boundaries, communication patterns, data ownership, and deployment constraints."
user-invocable: true
disable-model-invocation: false
---

# Microservices Architecture

## Purpose

Use this skill to split a system into smaller, independently deployable services without creating unnecessary complexity. The goal is to align each service to a bounded context, support independent delivery, and maintain clear contracts between teams and components.

## When to Use

Use this skill when you need to:
- decouple business domains into services
- improve scalability and deployment independence
- support multiple teams owning separate capabilities
- reduce risk in large or evolving applications
- separate synchronous APIs from asynchronous integration patterns

## Core Workflow

1. Define the business domains
   - Identify the major capabilities the application must support.
   - Group features by responsibility, not by technical layer alone.
   - Map each domain to a clear business context or bounded context.

2. Define service boundaries
   - Decide what belongs in each service based on business ownership and data ownership.
   - Keep each service responsible for one coherent capability.
   - Avoid splitting by database table or technical artifact alone.

3. Design contracts and communication
   - Choose API and event contracts between services.
   - Prefer asynchronous messaging for loosely coupled workflows when appropriate.
   - Document versioning, schemas, error handling, and operational expectations.

4. Handle cross-cutting concerns
   - Plan for authentication, logging, tracing, configuration, retries, and monitoring.
   - Standardize observability and health checks across services.
   - Keep platform concerns consistent without centralizing domain logic.

5. Design for resilience and operations
   - Add timeouts, circuit breakers, retries, queueing, and fallback strategies where needed.
   - Define deployment, scaling, and rollback plans for each service.
   - Ensure failure isolation rather than cascading failures across the platform.

6. Validate the architecture
   - Check that services can evolve independently.
   - Confirm each service has clear ownership, APIs, and data boundaries.
   - Review whether the architecture still remains understandable and operationally manageable.

## Decision Points

- If a domain is tightly coupled and changes often together, it may belong in the same service.
- If the system has a single database shared across many features, split the model by ownership before splitting the code.
- If synchronous communication is too brittle, move coordination to events or message-driven flows.
- If service boundaries are unclear, reduce scope and define a single domain first before expanding.
- If the architecture creates more operational overhead than business value, consider a modular monolith before full microservices.

## Practical Guidance

- Prefer bounded contexts and clear ownership over a technically attractive but misaligned decomposition.
- Keep service contracts explicit and version-aware.
- Treat data as owned by a specific service unless a deliberate shared pattern is required.
- Standardize observability, security, and deployment tooling across all services.
- Avoid premature decomposition when a simpler architecture meets the current scale and team needs.

## Quality Criteria

A microservices design is successful when:
- services have clear boundaries and ownership
- data ownership is explicit and consistent
- inter-service contracts are stable and well documented
- failure isolation and resilience are built in
- deployment and monitoring remain manageable as the system grows

## Expected Output

When using this skill, provide:
- the bounded contexts and service list
- the communication model and service contracts
- data ownership and integration decisions
- resilience, deployment, and observability recommendations
- any risks or trade-offs for the proposed architecture
