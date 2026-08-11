---
name: kiss-principles
description: "Use when: you need to simplify software design, code, and processes so solutions stay easy to understand, maintain, and evolve."
---

# KISS Principles

## Purpose

Use this skill to keep software solutions simple and practical. The goal is to avoid unnecessary complexity, prefer clear implementations, and make the solution easy to read, extend, and maintain.

## When to Use

Use this skill when you need to:
- simplify a feature or module
- refactor unclear or over-engineered code
- choose between a simple and a more complex solution
- reduce maintenance burden and cognitive load

## Core Workflow

1. Understand the problem clearly
   - Identify the real requirement and avoid solving imaginary problems.
   - Focus on the smallest useful solution first.

2. Prefer the simplest reasonable approach
   - Choose the most straightforward implementation that satisfies the requirement.
   - Avoid abstractions, frameworks, or patterns unless they clearly add value.

3. Remove unnecessary complexity
   - Eliminate redundant code, over-generalization, and premature optimization.
   - Keep naming, structure, and flow easy to follow.

4. Evaluate the trade-off
   - Ask whether a more complex solution is truly justified by current needs.
   - If not, prefer the simpler option.

5. Verify the result
   - Ensure the implementation works correctly and remains easy to understand.
   - Check that the solution is maintainable for the next developer.

## Decision Points

- If a solution is harder to explain than the problem itself, simplify it.
- If code is trying to handle many hypothetical cases, reduce the scope to what is actually required.
- If a pattern or abstraction does not clearly improve clarity or flexibility, avoid it.
- If a change increases complexity without a clear benefit, reconsider the approach.

## Practical Guidance

- Keep functions and classes focused on one clear purpose.
- Favor readability over cleverness.
- Use straightforward control flow and direct naming.
- Solve the current problem before optimizing for future possibilities.
- Prefer small, understandable steps over big, abstract ones.

## Quality Criteria

A solution follows KISS when:
- it is easy to understand quickly
- it solves the current requirement without unnecessary machinery
- it is easier to maintain than the previous version
- it avoids over-engineering and premature abstraction
- it remains clear to someone reading it for the first time

## Expected Output

When using this skill, provide:
- the problem or complexity being simplified
- the simpler approach chosen
- the changes made to reduce complexity
- the verification result and any follow-up improvement ideas
