# Anti-Patterns to Avoid (Hard Rules)

If any of the following anti-patterns appear in code, design, or suggestions,
explicitly call them out and explain why they are problematic.
Offer a safer alternative and describe the trade-offs.

---

## Distributed Systems

- Treating a distributed system as if it were a monolith.
  - Assuming calls are reliable, fast, or ordered.
  - Ignoring retries, timeouts, and partial failure.

- Using synchronous request/response chains across multiple services.
  - Leads to cascading failures and poor resilience.

- Relying on exactly-once delivery semantics.
  - Prefer at-least-once delivery and idempotent consumers.

- Tight coupling via shared databases between services.
  - This is not microservices; it is a distributed monolith.

---

## Messaging & Events

- Publishing domain entities or internal models as events.
  - Events must be explicit contracts, not ORM snapshots.

- Using events as commands (or vice versa).
  - Commands express intent; events express facts.

- Ignoring event versioning.
  - Events must evolve backward-compatibly.

- Fire-and-forget messaging without observability.
  - Every message flow must be traceable.

- Assuming message order without enforcing it.
  - Order must be explicit or irrelevant.

---

## .NET & Application Design

- Sync-over-async (`.Result`, `.Wait()`).
  - Leads to deadlocks and thread starvation.

- Overusing abstraction layers without clear value.
  - "Just in case" abstractions rot quickly.

- Hiding business logic inside controllers or infrastructure code.
  - Business logic must be explicit and testable.

- Using static state or singletons for request-scoped data.
  - Breaks concurrency and scalability.

- Catching exceptions and swallowing them.
  - Errors must be observable and actionable.

---

## Data & Persistence

- Treating the database as the integration mechanism.
  - Integration should happen via APIs or messages.

- Relying on distributed transactions (2PC).
  - Prefer eventual consistency and compensating actions.

- Using ORMs without understanding generated queries.
  - Always reason about SQL and query behavior.

- Performing schema changes without migration strategy.
  - Schema evolution is part of the system design.

---

## Cloud & Infrastructure

- Long-lived secrets in configuration files or containers.
  - Always prefer managed identity / IAM roles.

- Hard-coding cloud provider specifics deep into business logic.
  - Keep cloud concerns at the edges.

- Designing for vertical scaling first.
  - Cloud systems must scale horizontally by default.

- Treating infrastructure as static.
  - Assume nodes, pods, and instances are disposable.

---

## Containers & Kubernetes

- Running containers as root.
  - Unnecessary security risk.

- Missing health checks or probes.
  - Leads to invisible failures and poor recovery.

- No resource requests/limits.
  - Causes noisy-neighbor and instability issues.

- Baking configuration or secrets into images.
  - Images must be environment-agnostic.

---

## Observability & Operations

- Logging without correlation IDs.
  - Makes distributed debugging nearly impossible.

- Relying on logs alone.
  - Metrics and traces are equally important.

- Ignoring operational concerns during design.
  - "We'll monitor it later" is not a strategy.

---

## Testing

- Only unit testing happy paths.
  - Failure modes must be tested.

- Mocking everything in integration tests.
  - Integration tests must touch real infrastructure.

- Treating tests as blockers instead of safety nets.
  - Tests should enable refactoring, not prevent it.

---

## Architecture & Process

- Big-bang rewrites.
  - Prefer incremental evolution.

- Premature optimization or over-engineering.
  - Optimize for clarity first; measure before optimizing.

- Copy-pasting patterns without understanding trade-offs.
  - Patterns are tools, not goals.

- Ignoring team maturity and operational capability.
  - Architecture must match the team's ability to run it.

---

# Response Expectations

When any anti-pattern is detected:
1. Explicitly name the anti-pattern.
2. Explain why it is risky in production.
3. Propose a safer alternative.
4. Describe the trade-offs of the alternative.
