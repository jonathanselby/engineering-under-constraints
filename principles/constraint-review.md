# Constraint Review

A compact review for modern software architecture derived from the historical studies in this repository.

Use it before adding infrastructure, abstraction or automation.

## 1. Mission

State the job in one sentence.

What must the system reliably do?

## 2. Hard constraints

List the limits that genuinely shape the design:

- latency;
- throughput;
- memory;
- cost;
- power/compute;
- network/connectivity;
- deployment environment;
- people/support;
- regulation;
- recovery time.

Separate real constraints from inherited assumptions.

## 3. Resource budgets

For each material resource, define an intended envelope.

```text
resource | normal | maximum | behaviour at limit
```

A limit without defined behaviour is only a future incident.

## 4. State

Identify the states that matter operationally.

For each:

- what creates it;
- what changes it;
- what is authoritative;
- how it is recovered;
- how an operator sees it.

## 5. Interfaces

Identify the joins most likely to dominate system reliability.

Ask:

- what assumptions cross the interface?
- what happens if one side is slow or unavailable?
- who owns compatibility?
- can either side be replaced independently?

## 6. Degraded operation

For each important dependency, answer:

> If this disappears, what useful function remains?

Define deliberate degradation before implementing retries and failover.

## 7. Human load

List decisions and repetitive actions expected from operators.

Separate:

- judgement that should remain human;
- mechanical coordination that could become deterministic;
- emergency recovery that should be rehearsed.

## 8. Environment test

Name the assumption most likely to fail outside the design room.

Examples:

- bandwidth will always be available;
- upstream latency will be stable;
- data will be clean;
- operators will notice a warning;
- a cloud service will always respond;
- a queue can grow indefinitely.

Test that assumption explicitly.

## 9. Removal test

For every major component or service ask:

> What breaks if we remove this?

If the answer is vague, the component may be accidental complexity.

## 10. Change test

Ask what happens if:

- load doubles;
- a provider changes;
- the original team leaves;
- the network partitions;
- an input is malformed;
- one dependency is down for a day;
- the system must be rebuilt from documentation.

## Review outcome

The review should finish with four short lists:

```text
KEEP      necessary and understood
SIMPLIFY  necessary but more complex than required
REMOVE    not justified by the mission
TEST      assumption not yet demonstrated
```

This is not an architecture scorecard. It is a forcing function for explicit decisions.
