---
name: git
description: 'Use Git for source control, branching, commits, reviews, and repository hygiene. Use when you need feature branches, pull requests, clean history, or team collaboration best practices in a software project.'
argument-hint: 'Describe the workflow need: branching model, commit hygiene, PR flow, or repository setup.'
user-invocable: true
disable-model-invocation: false
---

# Git Workflow and Repository Hygiene

## When to Use
- The project needs version control for code changes and collaboration.
- You need to create feature branches, review diffs, or prepare a pull request.
- A team wants a clean, understandable commit history and release flow.
- You need to manage branches consistent with the repository backlog process.

## Core Principles
- Keep commits small, descriptive, and focused on one change.
- Use branches to isolate work and reduce accidental merging.
- Prefer clear, reviewable diffs over large, opaque changes.
- Protect the main branch and use pull requests for validation and review.
- Keep history readable for future debugging and release tracing.

## Procedure
### 1. Start from a clean base
- Pull the latest state of the target branch.
- Confirm the working tree is clean before starting new work.
- Create a branch that matches the work being delivered.

### 2. Implement with disciplined commits
- Commit logical units of work rather than large mixed changes.
- Write meaningful commit messages that explain what changed and why.
- Avoid committing secrets, generated files, or unrelated config.

### 3. Review before merge
- Check the diff for completeness and correctness.
- Ensure tests, linting, or validation checks relevant to the change are satisfied.
- Confirm the branch addresses the associated specification or ticket.

### 4. Merge and clean up
- Use pull requests for review and approval before merging.
- Delete temporary branches after successful integration.
- Keep branch naming consistent with the project workflow.

## Quality Checklist
- Branch names are descriptive and consistent.
- Commits are focused and understandable.
- The diff is reviewable and scoped to the task.
- No secrets, debug code, or unrelated files are committed.
- Pull requests are used for merge approval and traceability.

## Example Prompts
- "Create a feature branch and review the workflow for this new API service."
- "Help me clean up commit history before opening a PR."
- "Recommend a branch naming pattern for spec-based development."

## Output Expectations
- branch strategy guidance
- clean commit practices
- review and merge workflow recommendations
