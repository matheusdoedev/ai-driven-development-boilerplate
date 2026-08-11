---
name: javascript
description: "Use when: you need to build frontend behavior with clear, maintainable, and modern JavaScript."
---

# JavaScript Frontend Skill

## Purpose

Use this skill to build interactive frontend behavior with JavaScript in a way that is clear, maintainable, and easy to extend. The focus is on writing practical code that supports user interactions without unnecessary complexity.

## When to Use

Use this skill when you need to:
- add interactivity to a webpage or web app
- handle DOM events, form behavior, or UI state changes
- create reusable frontend logic for components or widgets
- refactor messy JavaScript into clearer, more reliable code

## Core Workflow

1. Understand the interaction goal
   - Identify the behavior the user needs.
   - Clarify what should happen, when it should happen, and what data or state is involved.

2. Keep the implementation focused
   - Prefer straightforward logic over clever abstractions.
   - Use the simplest approach that clearly supports the required behavior.

3. Write maintainable frontend JavaScript
   - Keep code readable and organized.
   - Separate concerns where possible, especially between data, DOM updates, and event handling.
   - Favor predictable patterns over brittle shortcuts.

4. Improve robustness
   - Handle common edge cases such as empty data, missing elements, and user input errors.
   - Avoid relying on fragile assumptions about the DOM.
   - Make behavior resilient to changes in markup or state.

5. Verify the result
   - Check that the interaction works as intended.
   - Confirm the code remains readable and easy to maintain.
   - Ensure the solution does not introduce unnecessary complexity.

## Decision Points

- If the behavior is tied to a single UI element, keep the logic close to that element rather than over-generalizing it.
- If the same logic is needed in multiple places, consider a reusable function or component-friendly approach.
- If the code is becoming hard to follow, simplify the flow before adding more abstraction.
- If DOM manipulation becomes too complex, consider whether the structure or data model should be improved.
- If the behavior depends on asynchronous operations, handle loading, error, and success states clearly.

## Practical Guidance

- Prefer clear variable and function names that describe intent.
- Keep event handlers small and delegate complex behavior to helper functions.
- Use modern JavaScript features when they improve clarity and compatibility.
- Avoid unnecessary global state and keep scope as narrow as possible.
- Write code that is easy to test and reason about.

## Quality Criteria

A JavaScript frontend implementation is strong when:
- the interaction works reliably
- the code is readable and maintainable
- edge cases are handled thoughtfully
- the logic is appropriately scoped and not overly abstract
- the solution is easy to extend later

## Expected Output

When using this skill, provide:
- the frontend interaction goal
- the JavaScript code needed to implement it
- any robustness or maintainability improvements
- a brief explanation of the approach and key decisions
