---
name: html
description: "Use when: you need to create or revise web interfaces using semantic HTML, accessible structure, and clear content hierarchy."
---

# HTML Web Interface Skill

## Purpose

Use this skill to create web interfaces with semantic HTML that are easy to read, accessible, and maintainable. The focus is on structure over presentation, using meaningful elements that communicate page purpose and content relationships.

## When to Use

Use this skill when you need to:
- build or revise a webpage or web app interface
- create semantic markup for navigation, content, forms, and media
- improve accessibility and document outline quality
- replace generic container markup with more meaningful HTML elements

## Core Workflow

1. Understand the interface goal
   - Identify the page or section being built.
   - Clarify the primary user task, content hierarchy, and expected interaction.

2. Choose the right semantic structure
   - Prefer landmarks such as header, nav, main, section, article, aside, and footer.
   - Use headings in a logical order to reflect content importance.
   - Use lists, tables, and form controls that match the content they represent.

3. Write accessible and meaningful markup
   - Use semantic elements instead of relying on divs and spans when possible.
   - Provide descriptive labels for forms, buttons, and images.
   - Ensure content can be understood without visual styling alone.

4. Keep markup clean and purposeful
   - Avoid unnecessary wrappers and overly complex nesting.
   - Keep the structure aligned with the content and user intent.
   - Separate structure from styling and behavior.

5. Verify the result
   - Check that the markup reflects the content hierarchy clearly.
   - Confirm that interactive elements are labeled and accessible.
   - Ensure the structure remains simple and easy to maintain.

## Decision Points

- If the content is a standalone piece of information, consider article instead of a generic container.
- If the section groups navigation or primary actions, use nav or header appropriately.
- If the interface includes user input, use form, label, input, textarea, button, and fieldset as needed.
- If an image conveys meaning, provide meaningful alt text; if decorative, use empty alt text.
- If a layout is only for styling and has no semantic meaning, avoid forcing a semantic element where it does not fit.

## Practical Guidance

- Prefer semantic HTML before adding CSS classes or JavaScript hooks.
- Use heading levels in a logical sequence: h1 for the page title, followed by h2, h3, and so on.
- Use main once per page for the primary content area.
- Use section when grouping related content under a clear heading.
- Use button for actions and a for links to navigation or destinations.
- Use figure and figcaption for images or media that need explanatory context.

## Quality Criteria

A semantic HTML implementation is strong when:
- the structure matches the meaning of the content
- the page is understandable through markup alone
- users can navigate and interact with the interface more easily
- the code is readable, maintainable, and accessible
- unnecessary generic containers are avoided

## Expected Output

When using this skill, provide:
- the interface goal and content structure
- the semantic HTML markup for the page or component
- any accessibility improvements or labeling needed
- a brief explanation of why the chosen elements are appropriate
