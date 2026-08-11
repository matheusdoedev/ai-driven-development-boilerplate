---
name: dry-principles
description: "Use when: you need to reduce duplication in software design and implementation while keeping the solution clear, maintainable, and avoid over-abstraction."
---

# DRY Principles

## Purpose

Use this skill to reduce duplication in code, design, and process while keeping solutions maintainable. The goal is to avoid repeating the same logic, knowledge, or behavior in multiple places without creating unnecessary complexity.

## When to Use

Use this skill when you need to:
- remove duplicated logic or repeated code blocks
- improve consistency across similar features or modules
- prevent drift when the same rule is implemented in multiple places
- refactor toward a more maintainable and reusable design

## Core Workflow

1. Identify duplication clearly
   - Find repeated logic, configuration, rules, or behavior.
   - Distinguish true duplication from similar but intentionally different code.

2. Understand the real intent
   - Determine what the duplicated code is trying to achieve.
   - Make sure the shared abstraction will preserve the intended behavior.

3. Extract or centralize the shared concern
   - Move shared logic into a function, class, module, service, or shared configuration.
   - Keep the abstraction focused and understandable.

4. Preserve clarity
   - Avoid over-generalizing just to remove repetition.
   - Prefer a simple abstraction over an overly clever one.

5. Verify the result
   - Run relevant tests or validations.
   - Ensure the change improved maintainability without introducing new complexity.

## Decision Points

- If the same logic appears in multiple places and changes together, consolidate it.
- If the duplication is only superficial, keep it separate rather than forcing abstraction.
- If extracting shared logic makes the code harder to follow, reconsider the abstraction.
- If duplication is caused by repeated configuration or business rules, centralize that knowledge in one place.

## Practical Guidance

- Avoid copy-pasting logic across modules.
- Consolidate shared rules, constants, validators, and transformations.
- Reuse existing helpers or abstractions before introducing new ones.
- Keep shared code easy to test and easy to understand.
- Balance reuse with simplicity; DRY should not lead to over-engineering.

## Quality Criteria

A DRY improvement is successful when:
- repeated logic is centralized or removed
- the shared abstraction is clear and meaningful
- the solution is easier to maintain and less prone to inconsistency
- the code remains readable and not overly abstracted
- behavior remains correct after the refactor

## Expected Output

When using this skill, provide:
- the duplicated concern identified
- the shared abstraction or refactor applied
- the verification result
- any follow-up suggestions for further cleanup or reuse
