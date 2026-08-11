---
name: solid-principles
description: "Use when: you need to design, review, or refactor software so it follows SOLID principles—single responsibility, open-closed, Liskov substitution, interface segregation, and dependency inversion."
---

# SOLID Principles

## Purpose

Use this skill to guide design decisions, code reviews, and refactoring so software becomes easier to extend, test, and maintain. The workflow helps apply SOLID principles in a practical and incremental way rather than as abstract theory.

## When to Use

Use this skill when you need to:
- design a new module, class, or service
- refactor existing code that has become hard to change
- improve testability and maintainability
- review whether current architecture follows good object-oriented design principles

## Core Workflow

1. Understand the responsibility
   - Identify the feature, module, or behavior being changed.
   - Clarify the current problem: rigidity, fragility, duplication, or unclear boundaries.

2. Apply the principles one at a time
   - Start with the most relevant principle for the current issue.
   - Prefer small, targeted improvements over large rewrites.

3. Evaluate each design choice
   - Ask whether the component has a single responsibility.
   - Ask whether the design is open for extension but closed for unnecessary modification.
   - Ask whether substitutions preserve behavior and expectations.
   - Ask whether interfaces are focused and not overly broad.
   - Ask whether dependencies point to abstractions rather than concrete details.

4. Refactor incrementally
   - Introduce abstractions only where they improve clarity or flexibility.
   - Preserve behavior while improving structure.
   - Keep each change easy to verify.

5. Verify the result
   - Run relevant tests or validations.
   - Check that the design is easier to understand and evolve.
   - Ensure the change did not introduce unnecessary complexity.

## Decision Points

- If a class or module is handling multiple unrelated concerns, split responsibilities before adding more behavior.
- If adding a feature requires editing many existing places, consider extending behavior through abstraction rather than changing concrete implementations directly.
- If a subtype breaks expected behavior, revisit the inheritance or interface design.
- If an abstraction is too broad or forced, reduce it and keep interfaces minimal and focused.
- If high-level code depends directly on low-level details, introduce an abstraction to invert the dependency.

## Practical Guidance for Each Principle

- Single Responsibility Principle (SRP): A component should have one clear reason to change.
- Open/Closed Principle (OCP): Behavior should be extendable without rewriting core logic.
- Liskov Substitution Principle (LSP): Derived types must be substitutable for their base types without breaking expectations.
- Interface Segregation Principle (ISP): Prefer small, specific interfaces over large general-purpose ones.
- Dependency Inversion Principle (DIP): Depend on abstractions, not concrete implementations.

## Quality Criteria

A design change is successful when:
- each responsibility is clear and scoped
- the solution can be extended without excessive modification
- subtypes behave safely in place of their parent types
- interfaces are focused and useful
- dependencies are inverted where appropriate
- the code remains understandable and testable

## Expected Output

When using this skill, provide:
- the design issue or smell being addressed
- the SOLID principle(s) applied
- the refactoring or structural change made
- the verification result and any follow-up recommendations
