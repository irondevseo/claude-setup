# Security Rules

Enforce the following security rules in every code generation task.

## 1. Authentication & Authorization
- Never write hardcoded API keys, passwords, database passwords, or JWT secrets. Use environment variables.
- Validate JWT signatures, expiry, and payload structures on every protected endpoint.
- Enforce role check guards. Do not rely on client-side routing logic to hide/show pages for authorization.

## 2. Injection & XSS Defenses
- SQL Injection: Use parameterized queries or ORM queries. Never string-concatenate variables into SQL statements.
- NoSQL Injection: Sanitize inputs before passing them to Mongo query operators (e.g. prevent passing `{ "$gt": "" }`).
- XSS Prevention: Sanitize user-provided HTML before rendering (use libraries like DOMPurify or sanitize-html).

## 3. Data Protection & Auditing
- Mask sensitive fields (e.g. passwords, SSNs, credit card numbers) before saving to audit logs or outputting to server logs.
- Salt and hash passwords using secure modern algorithms (e.g. bcrypt or argon2).
- Mask user IDs or transaction IDs in logs if GDPR / CCPA constraints are present.

## 4. API Security Checklist
- Implement Rate Limiting on public/auth routes (e.g. login, forgot-password).
- Enforce CORS rules: restrict allowed origins instead of using `*`.
- Set secure HTTP headers (e.g., Helmet middleware).
