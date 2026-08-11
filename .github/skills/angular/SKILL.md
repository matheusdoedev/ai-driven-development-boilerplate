---
name: angular
description: "Use when: you need to build frontend applications with Angular using components, services, routing, forms, and reactive patterns."
---

# Angular Frontend Skill

## Purpose

Use this skill to build and improve Angular applications with a focus on maintainable architecture, clear component boundaries, effective services, and reliable user interactions. The goal is to create applications that are easy to understand, test, and extend.

## When to Use

Use this skill when you need to:
- create or update Angular components, modules, or applications
- structure features around reusable components and services
- implement routing, forms, APIs, and state flows
- refactor existing Angular code for clarity and maintainability

## Core Workflow

1. Understand the feature and user flow
   - Clarify the screen, behavior, data model, and expected interactions.
   - Identify whether the work involves UI logic, API calls, forms, routing, or shared state.

2. Structure the feature clearly
   - Split the feature into focused components and services.
   - Keep presentation and business logic separated.
   - Prefer modular organization over putting everything in one file.

3. Use Angular patterns intentionally
   - Use component inputs and outputs for parent-child communication.
   - Put reusable logic into services or shared utilities.
   - Use dependency injection, reactive patterns, and Angular forms appropriately.
   - Keep templates simple and readable.

4. Handle data and async behavior well
   - Manage loading, empty, and error states clearly.
   - Use RxJS carefully and avoid unnecessary complexity.
   - Keep subscriptions and lifecycle handling predictable.

5. Verify the result
   - Check that the feature works end-to-end.
   - Ensure components remain easy to test and extend.
   - Confirm the implementation follows Angular conventions and stays maintainable.

## Decision Points

- If a component is doing too much, split it into smaller components or move logic to a service.
- If data is reused across features, place it in a shared service or state abstraction rather than duplicating it.
- If a template becomes crowded, move logic into the component class or create a smaller child component.
- If asynchronous flows become hard to follow, simplify the stream logic and handle states explicitly.
- If the app needs shared state, choose the lightest appropriate approach, such as a service, signals, or NgRx only when justified.

## Practical Guidance

- Favor clear component responsibilities and descriptive names.
- Keep templates declarative and avoid complex inline logic when possible.
- Use Angular CLI conventions and feature/module boundaries consistently.
- Prefer typed data models and strong input validation.
- Keep change detection and performance concerns in mind without over-optimizing prematurely.

## Quality Criteria

An Angular implementation is strong when:
- the feature is easy to understand and maintain
- components and services have clear responsibilities
- forms, routing, and data flows behave predictably
- the code follows Angular conventions and remains extensible
- the solution supports the intended user experience without unnecessary complexity

## Expected Output

When using this skill, provide:
- the feature requirement and Angular architecture approach
- the component and service structure and implementation
- any routing, form, API, or state decisions
- a short explanation of why the solution is maintainable and aligned with Angular best practices
