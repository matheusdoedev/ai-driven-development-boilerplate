---
name: ansible
description: 'Use Ansible for configuration management, environment setup, automation, and repeatable system provisioning. Use when you need server setup, package installation, config drift prevention, or deployment automation for infrastructure.'
argument-hint: 'Describe the target hosts, required packages or configuration, environment, and whether this is server setup or deployment automation.'
user-invocable: true
disable-model-invocation: false
---

# Ansible Configuration Management

## When to Use
- The project needs repeatable configuration of servers or environments.
- You need to install packages, configure services, or enforce a consistent baseline.
- You want simple automation for environment setup without building a custom script-heavy workflow.

## Core Principles
- Keep playbooks declarative and readable.
- Separate inventory, variables, and tasks clearly.
- Prefer idempotent actions that can be safely re-run.
- Use least-privilege access and secure secret handling.

## Procedure
### 1. Define the target state
- Specify the hosts, groups, and desired configuration.
- Document the service roles and operating-system assumptions.
- Identify stateful resources and dependencies.

### 2. Write the playbook
- Use tasks, handlers, and variables to describe the target state.
- Group related configuration into roles when useful.
- Keep playbooks explicit and easier to audit.

### 3. Handle secrets safely
- Use encrypted files, environment variables, or secret stores instead of hardcoded credentials.
- Limit scope and ensure only required hosts receive sensitive values.

### 4. Validate and iterate
- Run the playbook in a non-production environment first.
- Confirm idempotence and expected final state.
- Adjust the automation based on actual runtime behavior.

## Quality Checklist
- Playbooks are idempotent and reproducible.
- Hosts and variables are clearly defined.
- Secrets are not stored in plaintext.
- Configuration drift is minimized.
- The setup is easy to validate and troubleshoot.

## Example Prompts
- "Create an Ansible playbook to configure a Linux server for a .NET service."
- "Review this configuration automation for idempotence and secret-handling issues."
- "Define a role-based Ansible setup for app and database hosts."

## Output Expectations
- Ansible inventory and playbook strategy
- role or task design for target environment setup
- secure configuration management guidance
