---
name: api-gateway-design-pattern
description: "Use when: you need to design an API gateway that centralizes routing, security, observability, rate limiting, and cross-cutting API concerns for microservices or distributed applications."
argument-hint: "Describe the upstream services, traffic shape, auth model, routing needs, and latency or security constraints."
user-invocable: true
disable-model-invocation: false
---

# API Gateway Design Pattern

## Purpose

Use this skill to design a gateway that sits in front of internal services and provides consistent entry points for clients. The gateway should simplify client access, enforce policy, and reduce duplicated concerns across individual services.

## When to Use

Use this skill when you need to:
- consolidate multiple backend services behind one public entry point
- apply authentication, authorization, rate limiting, and throttling consistently
- route traffic by path, host, or service domain
- transform or aggregate requests for different client types
- reduce direct exposure of internal service topology

## Core Workflow

1. Identify gateway responsibilities
   - Decide whether the gateway is primarily routing, policy enforcement, transformation, protocol translation, or aggregation.
   - Separate client-facing concerns from internal service concerns.

2. Map client and service traffic
   - Identify public APIs and the internal services they call.
   - Define versioning, routes, and required authentication scopes.

3. Design security and policy controls
   - Apply identity validation, authorization, IP controls, TLS, and rate limits.
   - Centralize request validation and sanitization where appropriate.

4. Plan routing and transformation
   - Decide how requests are mapped to specific services.
   - Define request/response transformations, header rewriting, and path conventions.

5. Design for resilience and performance
   - Add caching, circuit breaking, retries, timeouts, and fallback behavior where needed.
   - Keep latency goals clear for public and internal traffic.

6. Validate operational behavior
   - Confirm the gateway gives complete telemetry, traceability, and health visibility.
   - Ensure failure modes are clear and recoverable for both clients and services.

## Decision Points

- If clients need different API shapes per channel, evaluate a BFF pattern rather than a generic gateway-only design.
- If every service needs the same policy, centralize it in the gateway; if only one service needs it, keep it local.
- If the gateway becomes a business logic bottleneck, move business behavior back into services.
- If service topology changes frequently, design the gateway with stable public contracts and versioning.
- If the gateway is the only security boundary, ensure it enforces identity and authorization strongly.

## Practical Guidance

- Keep the gateway focused on cross-cutting concerns, not core domain logic.
- Prefer stable external contracts over internal implementation details.
- Centralize authentication, quotas, telemetry, and routing policy for consistency.
- Use a BFF when different frontends need very different API compositions.
- Avoid overloading the gateway with deep business rules or service-to-service orchestration.

## Quality Criteria

An API gateway design is successful when:
- clients access services through a consistent, secure front door
- routing and policy enforcement are centralized and observable
- internal service topology is hidden from external consumers
- latency, resilience, and request shaping meet performance expectations
- the gateway stays maintainable without becoming a monolithic choke point

## Expected Output

When using this skill, provide:
- the gateway scope and responsibilities
- routing and versioning strategy
- security and policy enforcement model
- performance and resilience decisions
- trade-offs between gateway, BFF, and direct service access patterns
