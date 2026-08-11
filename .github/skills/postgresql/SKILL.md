---
name: postgresql
description: 'Design, model, secure, and operate PostgreSQL databases for application services. Use when you need schema design, migrations, performance tuning, indexing, backup strategy, Docker setup, or relational data modeling in a secure production-ready system.'
argument-hint: 'Describe the application domain, entities, expected data volume, and deployment target (local, Docker, Azure, Kubernetes, or app service).'
user-invocable: true
disable-model-invocation: false
---

# PostgreSQL Database Design and Delivery

## When to Use
- The system needs a relational database for structured, transactional data.
- You need to model tables, indexes, constraints, and relationships.
- You are implementing a service in a stack that already uses PostgreSQL as the default relational database.
- You need to define migration scripts, local Docker setup, schema validation, or production hardening.
- The requirement includes data integrity, auditability, concurrency, or performance optimization.

## Core Principles
- Prefer PostgreSQL when data is highly structured and relational integrity matters.
- Model the domain around business entities, not database implementation details.
- Protect data with least-privilege access, encrypted transport, and secure defaults.
- Design for growth: indexes, constraints, and clear naming patterns should scale with the app.
- Treat migrations as versioned, reviewable, and reversible where possible.
- Validate the schema against acceptance criteria before finalizing the implementation.

## Procedure

### 1. Confirm whether PostgreSQL is the right fit
- Use PostgreSQL for transactional, structured, query-heavy domains.
- Choose it over NoSQL when strong relational consistency, joins, foreign keys, and reporting patterns are important.
- Confirm expected workload: OLTP, analytics, read-heavy, write-heavy, or mixed traffic.
- Capture assumptions around volumes, retention, and concurrency.

### 2. Define the domain model
- Identify the core entities and relationships.
- Convert use cases into tables, columns, and constraints.
- Prefer explicit, business-friendly names such as `user_account`, `order_item`, and `audit_log`.
- Use primary keys, foreign keys, unique constraints, enums, and check constraints to enforce validity.
- Capture required auditing fields such as `created_at`, `updated_at`, and `created_by` when appropriate.

### 3. Design a safe and normalized schema
- Normalize to remove unnecessary redundancy while avoiding overengineering.
- Add indexes only where query patterns justify them.
- Keep the schema readable and maintainable: one concern per table, clear column naming, sensible defaults.
- Define constraints to reject invalid states before data reaches the application layer.
- Consider partitions or time-based tables only when scale demands them.

### 4. Define migration strategy
- Use migration files under a versioned schema directory.
- Split schema creation, seed data, and optional backfill logic into separate, explainable steps.
- Always include rollback or downgrade guidance when possible.
- Keep migrations idempotent and safe for repeated environments.
- Validate migrations against fresh local environments before production deployment.

### 5. Secure the database
- Use separate roles for application access, admin access, and read-only reads where possible.
- Grant the minimum required privileges instead of broad `ALL PRIVILEGES` access.
- Store secrets in environment variables or a secure secret manager, never in source control.
- Enable TLS for remote connections and restrict network exposure.
- Configure connection pooling and timeouts for application reliability.
- Consider row-level security or logical separation for sensitive domains when required.

### 6. Optimize for performance
- Add indexes for frequent filters, joins, sorts, and uniqueness checks.
- Avoid premature optimization; measure query behavior with real access patterns.
- Review `EXPLAIN ANALYZE` output for slow queries.
- Watch for common issues such as unbounded scans, missing indexes, large bulk writes, and lock contention.
- Separate hot tables and large historical tables when necessary for maintainability.

### 7. Set up local and deployment environments
- Use Docker Compose or a local PostgreSQL service when building new services.
- Define environment variables for host, port, database name, username, password, and SSL configuration.
- Ensure application startup scripts and health checks work with the database service.
- For containerized workloads, keep the database service isolated and clearly documented.
- When deploying to Azure or Kubernetes, align connection, storage, backup, and monitoring settings with the target platform.

### 8. Validate before completion
- Confirm the schema satisfies the business requirements and acceptance criteria.
- Check that relationships, constraints, and indexes are consistent with real use cases.
- Verify successful migrations in a fresh local or test environment.
- Ensure backups, restore procedures, and operational runbooks are documented.
- Confirm the design includes security, observability, and disaster-recovery considerations.

## Decision Guidance

### Use PostgreSQL when:
- The domain is transactional and relational.
- The team needs consistent data integrity and complex joins.
- The product has predictable schema evolution requirements.
- The project is in a service-oriented or enterprise architecture where structured data matters.

### Avoid PostgreSQL when:
- The workload is primarily unstructured or schema-less document storage.
- The team needs a simple cache or ephemeral session store instead of durable relational storage.
- The data model is not yet stable and could benefit from a more flexible data store.

## Quality Checklist
Before considering a Postgres implementation complete, verify the following:
- Data model matches business requirements.
- Constraints and keys enforce integrity.
- Migrations are versioned and reproducible.
- User permissions follow least privilege.
- Sensitive data is protected and secrets are externalized.
- Performance-critical queries have indexes and are validated.
- Backup and restore plans are documented.
- Local and deployment environments are runnable and testable.

## Example Prompts
- "Design a PostgreSQL schema for a task management service with users, projects, tasks, and comments."
- "Create a migration plan for a service that stores orders, payments, and audit logs."
- "Review this schema for indexing, security, and performance issues."
- "Set up a Postgres Docker environment for a .NET API service with environment variables and health checks."
- "Recommend a secure PostgreSQL role model for a production application deployed on Azure."

## Output Expectations
When used in backlog or implementation work, this skill should generate or validate:
- A logical schema or ER structure
- Migration-ready table definitions
- Role and access model guidance
- Performance hotspots and index recommendations
- A short checklist of security and operational requirements

## Related Guidance
This skill pairs well with backend service architecture work, Docker environment setup, Azure deployment planning, and backlog spec implementation for structured data domains.
