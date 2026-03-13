---
paths:
  - "tests/**/*"
  - "**/*test*"
  - "**/*spec*"
---

# Testing Rules

## Structure

- Mirror the source directory structure in tests.
- Name test files: `test_<module>.py` (Python) or `<module>.test.ts` (TypeScript).
- Group tests by behavior, not by method.

## Writing Tests

- Each test should test ONE behavior.
- Use the Arrange-Act-Assert pattern.
- Name tests descriptively: `test_returns_404_when_user_not_found`.
- Use fixtures for shared setup. Avoid setup duplication.
- Mock external dependencies (APIs, databases, file systems).
- Never call real external services in unit tests.
- Test edge cases: empty input, null/None, boundary values, error conditions.

## What to Test

- Business logic and domain rules (always).
- API endpoints: status codes, response shape, error responses.
- Data transformations and validations.
- Error handling paths.

## What NOT to Test

- Framework internals or third-party library behavior.
- Simple getters/setters with no logic.
- Implementation details that may change.

## Running Tests

- Run the full test suite before committing.
- Fix broken tests immediately, never skip them.
- A test that passes but tests nothing is worse than no test.
