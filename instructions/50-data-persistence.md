# Data & Persistence

- Choose the simplest data store that meets requirements.
- For EF Core:
  - Avoid N+1 queries.
  - Use AsNoTracking for read-only operations.
  - Use explicit transactions when consistency matters.
- Design for schema evolution and migrations.
