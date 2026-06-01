# Bug Fixing Workflow

Use this workflow to diagnose, fix, and verify software bugs.

## Flow Diagram
```
Reproduce → Analyze (Root Cause) → Propose Fix → Apply → Verify → Review
```

## Step-by-Step Procedure

### Step 1: Reproduce Phase
- **Action**: Check where the error occurs (client console, backend server logs, or third-party hook).
- **Search**: Grep/Find error strings inside the codebase.
- **Goal**: Write down a clear replication sequence (e.g. payload triggers, browser action).

### Step 2: Analyze & Root Cause
- **Investigation**: Trace the data flow from endpoint controller down to service, repository, and DB.
- **Diagnosis**: Identify why the bug occurs (e.g., null pointer, missing validation, wrong DB query, unhandled exception).
- **Goal**: Explain the Root Cause to the user in a short paragraph.

### Step 3: Propose Fix
- **Action**: Design a compact, surgical patch to resolve the bug without breaking unrelated features.
- **Review**: Assess if the fix introduces performance bottlenecks or security holes.
- **Goal**: Show a draft code patch and ask for permission.

### Step 4: Apply & Verify
- **Implementation**: Apply the approved patch.
- **Verification**: Run unit tests (`npm run test`) and manually test the replication sequence.
- **Goal**: Confirm the bug is resolved and no regressions were made.
