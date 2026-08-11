---
name: css
description: "Use when: you need to style web interfaces with clear, maintainable, and modern CSS."
---

# CSS Web Interface Skill

## Purpose

Use this skill to create and refine CSS for web interfaces with a focus on clarity, maintainability, and user experience. The goal is to style content effectively without creating brittle or overly complex rules.

## When to Use

Use this skill when you need to:
- style a webpage or component with CSS
- create layouts, spacing, typography, and visual hierarchy
- improve maintainability and consistency of styles
- refactor messy or overly specific CSS into clearer rules

## Core Workflow

1. Understand the visual goal
   - Identify the UI element or page being styled.
   - Clarify the intended layout, tone, spacing, hierarchy, and interaction states.

2. Define a clear structure for the styles
   - Prefer a simple organization based on components, sections, or utility concerns.
   - Keep selectors meaningful and avoid unnecessary specificity.

3. Write maintainable CSS
   - Use clear property grouping and consistent formatting.
   - Favor reusable classes and predictable naming.
   - Keep styling aligned with the semantic HTML structure.

4. Improve consistency and readability
   - Use spacing, typography, and color systems intentionally.
   - Avoid duplication by combining related rules where appropriate.
   - Keep styles easy to scan and modify.

5. Verify the result
   - Check that the styling achieves the intended appearance.
   - Confirm the CSS is not overly complex or fragile.
   - Ensure the interface remains readable and accessible.

## Decision Points

- If a style applies to a single component, prefer a specific class over broad global selectors.
- If the same visual pattern appears in multiple places, consider a reusable class or shared rule.
- If a layout can be expressed with modern layout methods, prefer them over hacky positioning.
- If a rule is only needed for a temporary visual fix, consider whether the underlying structure should be improved instead.
- If styles are becoming hard to override, simplify the selector strategy.

## Practical Guidance

- Prefer semantic class names that describe purpose, not presentation alone.
- Use spacing and typography consistently to create visual hierarchy.
- Keep custom properties useful for repeated values such as colors, spacing, and breakpoints.
- Use layout techniques that support responsiveness and accessibility.
- Separate structure, appearance, and behavior rather than mixing concerns.

## Quality Criteria

A CSS implementation is strong when:
- the styles are easy to understand and maintain
- visual hierarchy is clear and intentional
- the design is consistent across components and pages
- the CSS avoids unnecessary complexity and repetition
- the interface remains accessible and responsive

## Expected Output

When using this skill, provide:
- the visual goal and layout requirements
- the CSS needed to implement the styling
- any improvements to maintainability or structure
- a brief explanation of the design choices made
