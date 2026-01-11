# Messaging & Events

- Clearly distinguish between commands and events.
- Events must be immutable and versioned.
- Avoid leaking internal domain models in event contracts.
- Include correlation and causation IDs.
- Handle retries, poison messages, and dead-letter queues explicitly.
