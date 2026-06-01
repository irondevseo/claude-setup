# Testing & Quality Gates

Enforce testing rigor before delivering any implementation.

## 1. Test Architecture
- **Unit Tests**: Mock database queries, cache connections, and external API requests. Keep execution fast (< 50ms per test).
- **Integration Tests**: Set up a clean test database (or in-memory store) to test routing logic and end-to-end controllers.
- **Test File Naming**: Match existing extensions: `[name].spec.ts`, `[name].test.ts`, or `[name].test.tsx`.

## 2. Coverage Requirements
- New modules must target:
  - **Branch coverage**: > 80%
  - **Line coverage**: > 90%
- Critical business paths (e.g. checkout, login, withdrawal) require 100% path coverage.

## 3. Test Cases Blueprint
Every unit test suite must cover:
- **Happy Path**: Verifies correct inputs return correct outputs (200 OK / 201 Created).
- **Edge cases**: Empty lists, null properties, boundary limits, out-of-range dates.
- **Validation Errors**: Verifies wrong format inputs are blocked (400 Bad Request).
- **Permission Errors**: Verifies unauthorized tokens are rejected (401 Unauthorized / 403 Forbidden).

## 4. Verification Execution
Run local tests before marking any implementation task as complete. 
- Example NestJS: `npm run test` or `npm run test:cov`.
- Example React: `npm run test` or `vitest run`.
Report the outcomes of these tests directly in your final verification statement.
