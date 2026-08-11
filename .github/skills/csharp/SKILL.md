---
name: csharp
description: "Use when: you need to build reliable backend, CLI, or application logic in C# with clear architecture and maintainable code."
---

# C# Development Skill

## Purpose

Use this skill to build maintainable C# code for services, libraries, and application logic. The focus is on correctness, readability, and design that can evolve without accumulating technical debt.

## When to Use

Use this skill when you need to:
- implement business logic in .NET or C#
- create or update classes, services, APIs, or CLI applications
- design data models and workflows
- refactor C# code toward cleaner separation of concerns

## Core Workflow

1. Understand the requirement
   - Identify the behavior the application needs to support.
   - Clarify the inputs, outputs, constraints, and edge cases before writing code.

2. Model the domain clearly
   - Separate domain logic from infrastructure concerns when practical.
   - Use well-named types, interfaces, and services to reflect the actual business capability.

3. Keep the implementation focused
   - Prefer straightforward logic over clever abstractions.
   - Keep methods small, explicit, and aligned with a single responsibility.

4. Use modern C# patterns intentionally
   - Leverage nullable reference types, async/await, records, and enums when they improve clarity and safety.
   - Keep code idiomatic without overusing advanced features for their own sake.

5. Verify the result
   - Run the relevant build or tests for the behavior being changed.
   - Confirm the implementation remains readable, maintainable, and easy to extend.

## Decision Points

- If a class is doing too many unrelated things, split it into smaller responsibilities.
- If business rules are mixed into infrastructure code, move them into domain logic or application services.
- If repeated logic appears in multiple places, centralize it in a helper or shared abstraction when it improves clarity.
- If async code is used, ensure cancellation and failure handling are explicit and predictable.
- If state is shared too widely or mutated unpredictably, narrow the scope or refactor toward clearer ownership.

## Practical Guidance

- Prefer clear, descriptive names for types, methods, and variables.
- Keep constructors, methods, and properties focused and easy to reason about.
- Validate inputs and handle failure paths explicitly instead of relying on hidden assumptions.
- Use interfaces or abstractions for external dependencies such as repositories, clients, and services.
- Favor simple, testable logic over unnecessary abstraction or over-engineering.
- Write code that is easy to read in isolation and easy to debug when something fails.

## Quality Criteria

A C# implementation is strong when:
- the code behaves correctly for the intended use case
- responsibilities are well separated and easy to follow
- the design remains maintainable as requirements evolve
- edge cases and failure paths are handled thoughtfully
- the solution is easy to test and extend

## Expected Output

When using this skill, provide:
- the business or technical requirement being solved
- the C# implementation needed to address it
- any important design decisions around architecture, state, or dependencies
- a brief explanation of why the approach is maintainable and reliable
