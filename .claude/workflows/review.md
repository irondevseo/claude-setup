# Code Review & Delivery Workflow

Use this workflow to review local modifications before concluding work.

## Checklist Dimensions

### 1. Code Quality & Standards
- [ ] Variables/Functions are named clearly and match casing patterns (e.g., camelCase for JS/TS).
- [ ] No hardcoded numbers or magic strings (extract to constants).
- [ ] Functions are short, clean, and have single responsibilities.

### 2. Typings & Compilations
- [ ] Strict type checks pass (no implicit `any` in TS).
- [ ] No unused imports, variables, or functions.

### 3. Security Checks
- [ ] Input data is validated and sanitized (no injection risks).
- [ ] Authorization checks are integrated (Role guards / owner checks).
- [ ] Sensitive details are excluded from server logs.

### 4. Database Optimization
- [ ] Database queries are indexed. No select-all statements unless mandatory.
- [ ] Soft delete is respected in queries if configured.

### 5. Testing
- [ ] New code is covered by unit tests.
- [ ] Tests run successfully.

## Verification Report
Present the review output in the following format:
```markdown
### 🔍 Code Review & Verification Report

#### 1. Code Quality
- [Verdict] (e.g., PASS / FLAG / ACTION NEEDED)
- Notes: ...

#### 2. Typings & Compilation
- [Verdict]
- Notes: ...

#### 3. Security Checklist
- [Verdict]
- Notes: ...

#### 4. Test Coverage
- [Verdict]
- Notes: ...

*Mọi thứ đã sẵn sàng. Bạn có thể tiến hành commit mã nguồn.*
```
