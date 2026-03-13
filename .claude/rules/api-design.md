---
paths:
  - "src/**/routes/**"
  - "src/**/routers/**"
  - "src/**/endpoints/**"
  - "src/**/controllers/**"
  - "src/**/api/**"
---

# API Design Rules

## REST Conventions

- Use plural nouns for resources: `/users`, `/orders`.
- Use HTTP methods correctly: GET (read), POST (create), PUT (replace), PATCH (update), DELETE (remove).
- Return appropriate status codes: 200, 201, 204, 400, 401, 403, 404, 409, 422, 500.
- Use consistent error response format across all endpoints.

## Request/Response

- Validate all input at the API boundary.
- Use request/response schemas (Pydantic models, Zod schemas).
- Never expose internal IDs or implementation details in responses.
- Paginate list endpoints. Use cursor-based pagination for large datasets.

## Naming

- Use snake_case for JSON fields (Python) or camelCase (TypeScript/JS).
- Be consistent within the project. Pick one convention and stick to it.
- URL paths are always kebab-case.

## Security

- Never trust client input. Validate and sanitize everything.
- Use authentication middleware, not per-endpoint checks.
- Never log sensitive data (passwords, tokens, PII).
- Rate limit public endpoints.
