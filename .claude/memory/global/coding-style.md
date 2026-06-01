# Coding Style Guidelines

Adhere to these coding standards to maintain consistency across developers and agent runs.

## 1. Quality Priorities
Code must be written with the following priorities:
1. **Readability**: Code should read like well-written prose. Use descriptive names.
2. **Maintainability**: Design for the next developer. Use clear modular separations.
3. **Testability**: Avoid side-effects. Prefer pure functions where possible.
4. **Simplicity**: Do not over-engineer. Avoid complex patterns if a simple one works.

## 2. Naming Conventions
- **Files & Directories**:
  - React Components: PascalCase (e.g. `UserTable.tsx`, `LoginForm/index.tsx`).
  - Standard files: kebab-case (e.g. `user-service.ts`, `auth-guard.ts`).
- **Variables & Functions**: camelCase (e.g. `getUserById`, `isLoading`).
- **Classes & Types/Interfaces**: PascalCase (e.g. `UserService`, `UserDto`, `IUser`).
- **Database Tables/Collections**: snake_case / plural (e.g. `users`, `order_items`).

## 3. Idiom Preferences
- **TypeScript**:
  - Enforce strict typing. Do not use `any`. Use `unknown` or concrete types instead.
  - Export types cleanly. Prefer interfaces for object definitions.
- **Async Code**:
  - Use `async/await` syntax. Do not mix with `.then().catch()` chains unless handling specific library wrappers.
  - Implement timeout wrappers on external API calls.
- **Functional style**:
  - Prefer immutable operations (`map`, `filter`, `reduce`) over manual `for` loops.
