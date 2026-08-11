---
name: hexagonal-architecture
description: "Use when: you need to design or refactor software so business logic is isolated from infrastructure concerns using ports and adapters."
---

# Hexagonal Architecture

## Purpose

Use this skill to design or refactor software so the core business logic remains independent from delivery mechanisms, databases, frameworks, and external services. This helps keep applications easier to test, evolve, and adapt over time.

## When to Use

Use this skill when you need to:
- design a new feature around clear business rules
- refactor code that mixes domain logic with infrastructure concerns
- improve testability and maintainability of an application
- make it easier to swap databases, APIs, or UI implementations

## Core Workflow

1. Identify the core domain
   - Define the business capability or use case that must be preserved.
   - Keep the domain model and business rules centered around the problem, not the implementation details.

2. Define ports
   - Identify the interactions the application needs from the outside world.
   - Express those interactions as abstractions such as interfaces or contracts.

3. Implement adapters
   - Create concrete implementations for persistence, APIs, messaging, UI, or other external systems.
   - Keep adapters thin and focused on translating between the outside world and the domain ports.

4. Protect the domain from infrastructure
   - Ensure business logic depends on ports rather than concrete frameworks or services.
   - Avoid leaking database, HTTP, or framework details into the core layer.

5. Verify the separation
   - Check that the domain can be tested without real infrastructure dependencies.
   - Confirm that swapping adapters does not require rewriting the core logic.

## Decision Points

- If business logic depends directly on a framework or database implementation, introduce a port and move the dependency behind it.
- If a feature requires a new external integration, add an adapter rather than coupling the core to that integration.
- If the domain model starts to know about transport or storage details, refactor toward clearer abstractions.
- If a change requires modifying core logic just to swap delivery mechanisms, the architecture likely needs better separation.

## Practical Guidance

- Keep the domain layer focused on business rules and use cases.
- Put persistence, UI, messaging, and external services in adapter layers.
- Use interfaces or contracts to define the boundary between the domain and the outside world.
- Prefer small, explicit adapters over large infrastructure-aware components.
- Design around behavior and use cases rather than framework-specific implementations.

## Quality Criteria

A hexagonal design is successful when:
- business rules are isolated from infrastructure details
- the core can be tested without external systems
- adapters are simple and interchangeable
- changing infrastructure does not require changing the domain logic
- the architecture remains clear and understandable

## Expected Output

When using this skill, provide:
- the domain capability or use case being modeled
- the ports and adapters identified or introduced
- the refactoring or architectural change made
- the verification result and any follow-up recommendations
