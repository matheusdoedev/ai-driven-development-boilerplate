---
name: react
description: "Use when: you need to build or improve frontend applications with React components, state, and props."
---

# React Frontend Skill

## Purpose

Use this skill to build and refine React applications with a focus on clear component structure, predictable state management, and maintainable UI logic. The goal is to create components that are easy to understand, reuse, and extend.

## When to Use

Use this skill when you need to:
- create or update React components
- manage state, props, and events in a frontend app
- structure a React application around reusable UI pieces
- refactor React code to make it easier to maintain

## Core Workflow

1. Understand the UI requirement
   - Identify the component or page being built.
   - Clarify the user-facing behavior, data needed, and expected interactions.

2. Define a clear component structure
   - Break the UI into small, focused components.
   - Keep responsibilities simple and avoid combining unrelated behavior in one component.

3. Manage state intentionally
   - Keep state as local as possible.
   - Lift state only when multiple components need to share it.
   - Prefer simple, predictable state updates over overly complex logic.

4. Build reusable and readable components
   - Use props clearly and keep interfaces minimal.
   - Avoid unnecessary abstraction when a simple component is enough.
   - Keep component logic easy to follow.

5. Verify the result
   - Check that the component renders correctly and behaves as intended.
   - Confirm the implementation is understandable and maintainable.
   - Make sure the structure can be extended without major refactoring.

## Decision Points

- If a component is doing too many things, split it into smaller components.
- If state is only needed by one component, keep it local instead of lifting it unnecessarily.
- If props are becoming hard to manage, consider whether the component should be reorganized or whether a shared state pattern is needed.
- If a feature requires complex state transitions, simplify the flow before adding more abstraction.
- If the UI can be expressed with composition, prefer composition over deeply nested conditional logic.

## Practical Guidance

- Prefer simple functional components when they fit the use case.
- Use descriptive names that reflect the component’s purpose.
- Keep JSX readable and avoid deeply nested conditionals when possible.
- Handle loading, empty, and error states clearly.
- Separate presentational components from logic-heavy ones when useful.

## Quality Criteria

A React implementation is strong when:
- components are focused and easy to understand
- state is managed intentionally and predictably
- the UI is easy to extend and reuse
- the code remains readable without excessive abstraction
- the solution supports the intended user experience clearly

## Expected Output

When using this skill, provide:
- the UI requirement and component goal
- the React component structure and implementation
- any state, props, or interaction decisions
- a short explanation of why the approach is maintainable
