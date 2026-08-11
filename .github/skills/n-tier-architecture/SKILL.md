---
name: n-tier-architecture
description: "Use when: you need to design a layered application architecture that separates presentation, business logic, data access, and infrastructure concerns for maintainability and scalability."
argument-hint: "Describe the application type, layer boundaries, data persistence needs, and required deployment or scaling constraints."
user-invocable: true
disable-model-invocation: false
---

# N-Tier Architecture

## Purpose

Use this skill to organize an application into distinct logical layers so each tier has a clear responsibility. This helps teams build maintainable systems with cleaner boundaries, easier testing, and more predictable scaling.

## When to Use

Use this skill when you need to:
- structure a new application with clear separation of concerns
- improve maintainability in an existing monolithic application
- organize business logic, persistence, and UI responsibilities
- align application layers with team ownership and deployment boundaries
- prepare a solution for predictable growth and modular evolution

## Core Workflow

1. Define the application layers
   - Identify the presentation, application/business, domain/service, data access, and integration layers.
   - Clarify the role of each tier and what it should not own.

2. Establish responsibilities
   - Keep UI logic focused on user experience and interaction.
   - Keep business logic in a dedicated application or domain layer.
   - Keep persistence and external integration concerns in infrastructure or data access layers.

3. Create clear boundaries
   - Define interfaces and contracts between layers.
   - Prevent lower layers from leaking implementation details upward.
   - Ensure dependencies point inward when possible.

4. Design for testability and scale
   - Make each layer independently testable.
   - Ensure infrastructure concerns can be replaced or mocked without rewriting business logic.
   - Consider whether the architecture should remain monolithic or later split into services.

5. Validate operational behavior
   - Confirm security, performance, and monitoring are aligned with the layer boundaries.
   - Review whether the architecture can support expected load, maintainability, and team structure.

## Decision Points

- If business logic is mixed into controllers, UI, or database code, move it to a dedicated application/domain layer.
- If persistence logic is spread across many modules, centralize it behind repositories or data access abstractions.
- If the application must change often in multiple areas, simplify the layer boundaries to reduce accidental coupling.
- If the app is small and the team is small, a lean 3-tier design may be enough; do not over-engineer the layers.
- If growth requires independent scaling or ownership, consider splitting the application into services while preserving the same layered principles.

## Practical Guidance

- Prefer clear interfaces over broad shared dependencies.
- Keep domain logic independent from UI and infrastructure details.
- Standardize how each layer communicates with the next.
- Use a layered architecture as a maintainability tool, not as a rigid formula.
- Keep the design proportional to the system’s real complexity.

## Quality Criteria

An n-tier design is successful when:
- each layer has a distinct responsibility
- business logic is not entangled with data or UI concerns
- interfaces and contracts are explicit and stable
- the solution is testable, scalable, and maintainable
- team ownership aligns with architectural boundaries

## Expected Output

When using this skill, provide:
- the layer model and responsibilities
- cross-layer contracts and boundaries
- the technology choices and dependency flow
- deployment and scaling implications
- any trade-offs or future evolution recommendations
