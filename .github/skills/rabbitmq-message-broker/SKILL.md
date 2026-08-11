---
name: rabbitmq-message-broker
description: "Use when: you need to design asynchronous messaging flows with RabbitMQ for decoupling services, reliable queueing, event-driven workflows, and message processing."
argument-hint: "Describe the publishers, consumers, message types, reliability requirements, throughput expectations, and failure handling strategy."
user-invocable: true
disable-model-invocation: false
---

# RabbitMQ Message Broker

## Purpose

Use this skill to design and implement messaging flows with RabbitMQ when components need to communicate asynchronously, decouple producers from consumers, or distribute work reliably across services.

## When to Use

Use this skill when you need to:
- decouple synchronous request processing from background work
- deliver events to multiple consumers or downstream services
- process jobs, workflows, or notifications asynchronously
- support retries, dead-letter handling, or buffering under load
- build event-driven integrations between services

## Core Workflow

1. Define the messaging pattern
   - Decide if the system needs point-to-point work queues, publish/subscribe events, or both.
   - Choose durable exchanges, queues, and routing semantics that fit the use case.

2. Model message contracts
   - Define message payloads, correlation IDs, timestamps, and versioning.
   - Keep messages explicit, traceable, and backward compatible where possible.

3. Design broker topology
   - Map publishers, exchanges, queues, routing keys, and consumer groups.
   - Use fanout or topic exchanges for broadcast events and direct/queue patterns for work distribution.

4. Handle reliability and failure modes
   - Configure durable queues, acknowledgements, publisher confirms, and re-queue behavior.
   - Add dead-letter exchanges and retry policies for poison messages and transient failures.

5. Plan consumer behavior
   - Make consumers idempotent and safe to retry.
   - Define maximum retries, visibility timeouts, and backoff strategies.
   - Avoid processing the same message twice without safe reconciliation.

6. Validate observability and operations
   - Confirm queue depth, throughput, retries, and DLQ metrics are available.
   - Add alerting and operational actions for broker congestion or consumer failure.

## Decision Points

- If a task must be processed eventually and can tolerate delay, prefer RabbitMQ queues over synchronous API calls.
- If multiple consumers need the same event, use a publish/subscribe or fanout pattern.
- If message ordering matters for a specific business flow, design a single consumer or partitioned sequence rather than an unbounded broadcast topology.
- If consumer errors are repeated, route failed messages to a dead-letter flow for investigation instead of retrying indefinitely.
- If the system needs synchronous request/response, avoid message broker usage unless a decoupled async flow is genuinely required.

## Practical Guidance

- Keep payloads small and schema-aware.
- Separate business events from command messages so consumers know the intent clearly.
- Prefer explicit retry and DLQ policies over silent message loss.
- Use idempotency keys or deduplication where duplicate consumption is possible.
- Monitor consumer lag and queue backlog before scaling or adding more workers.

## Quality Criteria

A RabbitMQ design is successful when:
- messaging contracts are explicit and versioned
- producers and consumers are decoupled safely
- reliability and retries are configured appropriately
- failed messages are observable and recoverable
- operational metrics and alerting support broker health and throughput management

## Expected Output

When using this skill, provide:
- the messaging pattern used and why
- exchange, queue, and routing topology
- message schema and versioning strategy
- reliability, retry, DLQ, and idempotency design
- monitoring and operational guidance for the broker and consumers
