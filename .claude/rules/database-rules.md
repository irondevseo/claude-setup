# Database Rules (SQL & NoSQL)

Manage database changes, schemas, and performance safely.

## 1. Migration Safety
- Never perform destructive changes (e.g. dropping a column/table, renaming columns) in production without a dual-phase deployment strategy:
  1. Add new column/table, write to both, run backfill script.
  2. Deprecate and remove old column/table in the next release.
- Always check that migrations can be rolled back safely.

## 2. PostgreSQL & SQL Rules
- Every table must have a primary key, `created_at` (timestamptz), and `updated_at` (timestamptz).
- Foreign keys must be indexed to prevent locking issues on joins.
- Use constraints (`UNIQUE`, `CHECK`) to enforce integrity.

## 3. MongoDB & NoSQL Rules
- Every document must conform to a schema validator.
- Define compound indexes for queries that filter by multiple fields (e.g. `{ userId: 1, status: 1 }`).
- Never perform unbounded array pushes. If an array attribute can grow past 100 entries, split it into a separate collection.

## 4. Query Performance
- Run `EXPLAIN ANALYZE` (SQL) or `.explain("executionStats")` (MongoDB) on slow or high-throughput queries.
- Do not run business calculations in raw database queries unless highly optimized (prefer aggregating in memory or background workers).
