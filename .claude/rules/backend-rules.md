# Backend Quality Rules (NestJS & NodeJS)

Adhere to these rules when writing backend code.

## 1. DTO & Validation
- Class-based DTOs are mandatory for all controllers.
- Use `class-validator` decorators for validation (e.g. `@IsString()`, `@IsEmail()`, `@IsOptional()`).
- Always whitelist and forbid unknown properties:
  ```typescript
  new ValidationPipe({ whitelist: true, forbidNonWhitelisted: true })
  ```

## 2. API Documentation (Swagger)
- Every public controller method must have Swagger decorators (`@ApiOperation`, `@ApiResponse`, `@ApiBody`).
- Declare data models using `@ApiProperty()` in DTOs.

## 3. Exception Handling
- Do not catch exceptions without logging them.
- Throw NestJS built-in exceptions (`NotFoundException`, `BadRequestException`, `ForbiddenException`, `InternalServerErrorException`) instead of custom error strings.
- Never bubble up database client exceptions (e.g. raw Prisma or MongoDB driver errors) directly to the user.

## 4. Query & Database
- Always check indexes on queries in loops or heavy lists.
- Avoid using `Select *` or equivalent ORM selects where only a few fields are needed. Use projections/select statements.
- Avoid pagination memory bottlenecks by using Cursor pagination (`limit`/`cursor`) instead of offset-based queries on large datasets (100k+ rows).
