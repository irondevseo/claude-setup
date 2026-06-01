# Requirement Gate Rule

A feature cannot transition from the **Discovery Phase** to **Architecture Phase** unless all critical business variables are fully answered and mapped.

## Mandatory Information Matrix
The table below specifies what *must* be known before proceeding. If any item is marked `MISSING`, the Orchestrator must block design and coding.

| Dimension | Required Details | Status |
| :--- | :--- | :--- |
| **Business Objective** | Why are we building this? What problem does it solve? | Awaiting Input |
| **Target User/Role** | Which actors have access? (Admin, Guest, User, Manager) | Awaiting Input |
| **Access Control** | Detailed permission rules (Who can Create, Read, Update, Delete) | Awaiting Input |
| **CRUD Definition** | Is it a full CRUD or just read-only/write-only? | Awaiting Input |
| **Query Fields** | Search criteria (exact match, full text) & filter facets (date, status) | Awaiting Input |
| **Data Lifecycle** | Status flow (e.g., Draft -> Pending -> Published) | Awaiting Input |
| **Database Actions** | Soft delete vs hard delete, Audit trail, Archiving decisions | Awaiting Input |
| **Validation Rules** | Fields format constraints (length, regex patterns, enum values) | Awaiting Input |
| **Third-Party / Assets** | External integrations, file uploads, notifications (email/SMS) | Awaiting Input |

## Verification Protocol
1. **Gather answers**: The Product Owner collects answers.
2. **Review inputs**: Compare answers against the matrix.
3. **Write Memory**: Save findings into `.claude/memory/feature/[feature-name].md`.
4. **Approve Gate**: Explicitly output a confirmation that the gate has passed:
   `[GATE PASSED] - All requirements clarified for [feature-name]. Handoff to Architect Agent.`
