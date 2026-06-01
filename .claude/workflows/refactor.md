# Refactoring Workflow

Use this workflow to optimize, clean up, or deprecate legacy modules.

## Flow Diagram
```
Impact Analysis → Refactoring Plan → Incremental Edits → Tests & Validation
```

## Step-by-Step Procedure

### Step 1: Impact Analysis
- **Action**: Locate every instance, file import, and function call that depends on the code block to be refactored.
- **Tools**: Use search, grep, or dependency trackers.
- **Risk Assessment**: Classify risk level:
  - **Low**: Local helper function (used inside one file).
  - **Medium**: Service method (used by multiple controllers).
  - **High**: Shared middleware, Auth logic, or base DB utility (used across the entire system).

### Step 2: Refactoring Plan
- **Action**: Outline a step-by-step modification checklist.
- **Avoid Big Bangs**: Break the changes down into small commits. For high-risk refactoring, write a wrapper or keep both old/new methods alive concurrently during migration.
- **Goal**: Share the plan with the user.

### Step 3: Incremental Edits & Compilation
- **Action**: Modify code chunks one by one.
- **Verification**: Run TypeScript compilation check or build script continuously to catch syntax/type mismatches early.

### Step 4: Verification & Test Execution
- **Action**: Run existing unit/integration tests to ensure no regressions were introduced.
- **Goal**: All tests pass. Share final diff statistics.
