# Web APIs (ASP.NET Core)

- Prefer Minimal APIs or Controllers consistently within a project.
- Follow REST principles where applicable, but prioritize clarity.
- Use ProblemDetails for error responses.
- Validate all inputs explicitly.
- Version APIs intentionally and document the strategy.

Authentication & Authorization:
- Assume OAuth2 / OIDC.
- Prefer policy-based authorization.
- Apply least-privilege principles.
