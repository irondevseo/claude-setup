# Feature Implementation Workflow

Use this workflow when creating a new module or a non-trivial functional block.

## Flow Diagram
```
Discovery → Architecture → Plan Approval → Implementation → Testing → Review
```

## Step-by-Step Procedure

### Step 1: Discovery Phase
- **Role**: Product Owner.
- **Trigger**: User requests a new feature.
- **Action**: Check `.claude/rules/requirement-gate.md` and ask 5-10 discovery questions. Do not write code.
- **Goal**: Gather all answers and save them to `.claude/memory/feature/[feature-name].md`.

### Step 2: Architecture Phase
- **Role**: Architect.
- **Trigger**: Requirement Gate passes.
- **Action**: Design database schemas, API routes, DTO payload rules, and code folder hierarchy.
- **Goal**: Propose layout structure and write it into the chat for user review.

### Step 3: Plan Approval Phase
- **Role**: Architect & User.
- **Trigger**: Architecture layout proposed.
- **Action**: Present the Step-by-Step Implementation Plan (WBS). Wait for the user to write "Approve" or provide feedback.
- **Goal**: Establish consensus on the scope.

### Step 4: Implementation Phase
- **Role**: Backend Lead & Frontend Lead.
- **Trigger**: Plan approved.
- **Action**: Create files, implement business logic, write database operations, and connect UI components. Follow `.claude/rules/backend-rules.md` and `.claude/rules/frontend-rules.md`.
- **Goal**: Build feature following approved plans.

### Step 5: Testing Phase
- **Role**: QA Lead / Developer.
- **Trigger**: Implementation complete.
- **Action**: Run tests (e.g. `npm run test`) and verify behavior against `.claude/rules/testing-rules.md`.
- **Goal**: Ensure no regressions, correct errors, and verify happy paths.

### Step 6: Review & Finalize Phase
- **Role**: CTO / Technical Lead.
- **Trigger**: Tests pass.
- **Action**: Inspect diff (`git diff`), audit security against `.claude/rules/security-rules.md`, and report code delivery details. Await user manual commit.
