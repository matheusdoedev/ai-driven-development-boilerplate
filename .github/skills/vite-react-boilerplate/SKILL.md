---
name: vite-react-boilerplate
description: "Use when: you need to scaffold or explain a Vite React starter application with a modern frontend setup."
---

# Vite React Boilerplate Skill

## Purpose

Use this skill to generate, explain, or refine a Vite-based React application starter structure. The focus is on providing a clean, modern frontend scaffold with React, Vite, and basic developer tooling.

## When to Use

Use this skill when you need to:
- create a Vite + React starter app
- initialize a frontend project with React and Vite tooling
- explain the files and structure of a Vite React boilerplate
- add or update basic React app setup and configuration

## Core Workflow

1. Confirm the project type and package manager
   - Use Vite with React, optionally TypeScript.
   - Identify whether npm, yarn, or pnpm is preferred.

2. Generate the boilerplate structure
   - Include `index.html`, `src/main.jsx`, `src/App.jsx`, `src/index.css`, and `vite.config.js` or `vite.config.ts`.
   - Include `package.json` with Vite, React, React DOM, and development dependencies.

3. Apply frontend best practices
   - Use semantic HTML in `App.jsx`.
   - Keep styling simple and maintainable.
   - Avoid unsafe inline scripting or event handlers.

4. Verify the starter works
   - Ensure development starts on `npm run dev` or equivalent.
   - Confirm the app renders a minimal homepage message.

## Decision Points

- If the user wants TypeScript, generate `.tsx` files and `tsconfig.json`.
- If the user needs a plain starter, keep the app minimal and focus on essential files.
- If a more opinionated setup is requested, include common developer scripts like `dev`, `build`, and `preview`.

## Practical Guidance

- Prefer a simple `App` component with clear semantic structure.
- Keep package dependencies minimal for a new project.
- Use Vite defaults unless the requirement calls for additional configuration.
- Ensure the starter is easy to extend with routes, state, or styling.

## Expected Output

When using this skill, provide:
- the recommended Vite React project structure
- the key files and their purpose
- minimal configuration for a working starter app
- any scripts or commands to run the boilerplate
