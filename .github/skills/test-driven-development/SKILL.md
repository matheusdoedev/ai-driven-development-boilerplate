---
name: test-driven-development
description: "Use when: you need to build or change a feature by following a strict TDD loop—write a failing test first, implement the smallest change to make it pass, refactor, and repeat until the requirement is complete."
---

# Test-Driven Development

## Purpose

Use this skill to build software features or requirements incrementally while keeping behavior verified at every step. The workflow favors small, testable changes over large speculative implementations.

## When to Use

Use this skill when you need to:
- implement a new feature or user story
- fix a bug with clear expected behavior
- add or update behavior while preserving existing functionality
- work in a codebase where regression safety matters

## Core Workflow

1. Understand the requirement
   - Read the request carefully and identify the smallest observable behavior to implement.
   - If the requirement is ambiguous, write down the acceptance criteria before coding.
   - Ask for clarification if the expected behavior is still unclear.

2. Write a failing test first
   - Add or update the smallest test that captures the requirement.
   - Prefer one behavior per test when possible.
   - Make the test specific enough to fail for the right reason.

3. Run the relevant tests
   - Execute the targeted test suite and confirm the new test fails.
   - If it passes unexpectedly, revise the test so it truly captures the missing behavior.

4. Implement the minimum code to make the test pass
   - Write the smallest possible production change.
   - Avoid expanding scope beyond the current requirement.
   - Keep the implementation simple and focused.

5. Re-run the tests
   - Verify that the new test passes and that related tests still pass.
   - If something breaks, fix the issue before moving forward.

6. Refactor safely
   - Improve structure, readability, or maintainability without changing behavior.
   - Re-run tests after refactoring to preserve correctness.

7. Repeat the cycle
   - Continue adding the next small behavior or requirement.
   - Stop only when the full requested scope is implemented and verified.

## Decision Points

- If the requirement is too broad, split it into smaller user-facing behaviors and tackle them one at a time.
- If the test fails for the wrong reason, fix the test or clarify the requirement before changing production code.
- If the implementation becomes too complex, reduce the scope and solve the next smallest step.
- If there is existing behavior that might be affected, run related tests before and after the change.

## Quality Criteria

A TDD cycle is complete only when:
- a test exists for the behavior being added or changed
- that test fails before the implementation is added
- the implementation is the smallest change needed to pass
- the relevant tests pass after the change
- the code is refactored safely without breaking existing behavior

## Expected Output

When using this skill, provide:
- the test added or updated
- the implementation change made to satisfy it
- the verification result from the relevant test run
- any follow-up work needed for the next TDD cycle
