---
name: git-flow
description: 'Use Git Flow branching patterns for feature development, release management, and environment-based delivery. Use when the team needs a predictable branch model for feature, release, hotfix, and maintenance work.'
argument-hint: 'Describe the delivery lifecycle, release cadence, and whether you need feature, release, or hotfix branch guidance.'
user-invocable: true
disable-model-invocation: false
---

# Git Flow Branching Strategy

## When to Use
- The team needs a clear branch model for feature development and release management.
- Work is delivered across multiple environments or stages.
- The project requires disciplined separation of ongoing development, hotfixes, and releases.

## Core Principles
- Keep production code stable and protected.
- Use short-lived branches for feature work.
- Separate development, release, and hotfix flows to reduce conflict and operational risk.
- Make merges intentional and reviewable.

## Procedure
### 1. Define the branch model
- Use `main` or `master` for production-ready code.
- Use `develop` or equivalent for active integration work.
- Create feature branches from the integration branch for new work.
- Use release branches for pre-production stabilization.
- Use hotfix branches for emergency fixes to production.

### 2. Deliver work through the model
- Branch from the right source depending on the task type.
- Keep branch scope narrow and aligned to one spec or issue.
- Merge only after validation and review.

### 3. Maintain release discipline
- Merge completed features into the development branch.
- Stabilize in a release branch before production deployment.
- Use hotfixes sparingly and merge them back into the active branches.

### 4. Review and cleanup
- Delete merged branches promptly.
- Keep naming conventions consistent with team practices.
- Ensure the main branch always reflects the most stable releasable state.

## Quality Checklist
- Branch roles are clearly defined and understood.
- Feature work is isolated and reviewable.
- Production is protected by intentional release flow.
- Hotfixes are handled with controlled and traceable merges.

## Example Prompts
- "Set up a Git Flow strategy for this project with feature, release, and hotfix branches."
- "Recommend how to integrate this spec into the repo using Git Flow."
- "Review this branch strategy for release safety and team collaboration."

## Output Expectations
- branch model guidance
- release and hotfix workflow recommendations
- delivery discipline for multi-environment software teams
