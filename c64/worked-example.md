# Worked Example — Applying C64 Discipline Without Copying C64 Design

Consider a fictional internal service that receives small work requests, applies a deterministic transformation and writes a result.

A modern implementation could easily accumulate a queueing platform, distributed cache, workflow engine, service mesh and multiple persistence layers before the workload requires them.

The C64-derived question is simpler:

> What does the smallest explicit execution model look like?

```text
REQUEST
  |
  v
VALIDATE
  |
  v
QUEUED WORK ITEM
  |
  v
PROCESS
  |
  +--> success --> RESULT
  |
  +--> failure --> FAILED ITEM
```

## Explicit state

Use a deliberately small state model:

```text
received -> accepted -> running -> completed
                         |
                         +-> failed
```

Do not infer state from scattered logs or side effects.

## Explicit budgets

Before scaling, choose finite defaults:

- maximum request size;
- maximum queued items;
- maximum worker count;
- maximum processing time;
- maximum result size.

These are not attempts to recreate 64 KB scarcity. They make overload behaviour a design decision.

## Small representation

A work item might contain only:

```text
id
created_at
state
input_reference
attempt
error
```

Add fields only when they support a real behaviour or decision.

## Rich behaviour from small mechanisms

With a queue, finite workers, explicit state and one durable result store, the service can already support:

- back-pressure;
- retries controlled by policy;
- observability by state;
- predictable restart behaviour;
- horizontal replication if load later requires it.

## The point

The historical lesson is not "use fewer bytes".

It is:

> **Start with explicit state, bounded resources and a comprehensible execution model. Add machinery when a demonstrated constraint earns it.**
