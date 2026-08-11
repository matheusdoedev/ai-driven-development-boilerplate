---
name: clean-code
description: "Use when: you need to apply clean code practices to improve readability, maintainability, and structure across codebases."
---

# Clean Code Skill

## Purpose

Use this skill to improve code quality by applying clean code practices and simplifying the implementation without sacrificing correctness. The focus is on naming, structure, readability, and preserving intent.

## When to Use

Use this skill when you need to:
- refactor code for readability and maintainability
- improve naming, structure, and separation of concerns
- simplify complex implementations and remove clutter
- apply consistent clean code principles across files or modules

## Core Workflow

1. Understand the code intent
   - Identify the purpose of the code and the behavior it needs to preserve.
   - Separate the core logic from incidental details.

2. Improve naming and structure
   - Use descriptive names for functions, variables, classes, and modules.
   - Keep functions small and focused on a single responsibility.

3. Clarify control flow
   - Avoid nested conditionals and deep branching where possible.
   - Use early returns, guard clauses, or helper functions to simplify flow.

4. Reduce duplication and coupling
   - Extract repeated logic into reusable functions or utilities.
   - Keep dependencies narrow and avoid leaking implementation details across boundaries.

5. Preserve behavior and verify
   - Ensure the refactor preserves existing behavior.
   - Prefer tests, examples, or type checks to confirm correctness.

## Decision Points

- If a function is doing too many things, split it into smaller, well-named helpers.
- If names do not express intent clearly, rename them before changing behavior.
- If branches or loops are hard to follow, refactor them into simpler constructs.
- If duplicated logic appears in multiple places, centralize it into a single, reusable implementation.
- If an abstraction makes the code harder to understand, prefer a more direct implementation.

## Practical Guidance

- Favor clarity over cleverness.
- Keep the public API of a module simple and stable.
- Use whitespace, line breaks, and formatting to make intent obvious.
- Write code that is easy for the next developer to read and reason about.
- Avoid premature optimization unless it is required by known constraints.

## Quality Criteria

Clean code changes are strong when:
- the solution is easier to read and understand
- responsibilities are separated clearly
- the code surface is less noisy and more expressive
- behavior remains correct and verifiable
- future changes are easier to make without introducing bugs

## Expected Output

When using this skill, provide:
- the clean code issue or opportunity identified
- the refactor or improvement applied
- the rationale for the chosen simplification
- the impact on readability, maintainability, and correctness
