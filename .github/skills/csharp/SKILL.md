---
name: csharp
description: "Use when: you need to build reliable backend, CLI, or application logic in C# with clear architecture and maintainable code."
---

# C# Development Skill

## Purpose

Use this skill to build maintainable C# code for services, libraries, and application logic. The focus is on correctness, readability, and design that can evolve without accumulating technical debt.

## When to Use

Use this skill when you need to:
- implement business logic in .NET or C#
- create or update classes, services, APIs, or CLI applications
- design data models and workflows
- refactor C# code toward cleaner separation of concerns

## Guidelines

- Use records in place of classes for DTOs and models;
- Use sealed records and classes when inheritance is not needed;
- Use interfaces to define contracts for services and repositories;
- Use `clean-code` principles to write readable and maintainable code;

### .NET Project Guidelines

- Use LTS versions;
- Use webapi template for APIs, and workers templates for background services;
- Use SAFE nuget dependencies only;
- Use Serilog as logging provider, and configure it to log to console and file;
- Use Dapper as database resources provider (for query, insert, update, delete operations);
