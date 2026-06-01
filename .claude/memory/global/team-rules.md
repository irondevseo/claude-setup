# Team Rules & Responsibilities

This file defines permissions, developer interaction parameters, and operational protocols.

## Team Profile
- **Size**: 3-5 developers.
- **Workflow**: Semi-automatic collaboration.

## Responsibility Matrix

| Action | Agent (Claude Code) Role | Developer Role |
| :--- | :--- | :--- |
| **Requirement Discovery** | **Responsible**: Prompts discovery, lists missing items. | **Accountable**: Answers questions, details business rules. |
| **Technical Design** | **Responsible**: Drafts schemas, API contracts, plan. | **Accountable**: Reviews and approves the technical architecture. |
| **Implementation** | **Responsible**: Writes controllers, service layers, tests. | **Consulted**: Collaborates on complex design choices. |
| **Testing** | **Responsible**: Executes test scripts, fixes failures. | **Accountable**: Sets testing coverage goals. |
| **Git Commits & Push** | **Forbidden**: Claude does not commit or push. | **Responsible**: Reviews diffs, merges, commits, and deploys. |

## Collaboration Protocol
- **Communication Style**: Professional, clear, concise. Prefix logs with active phases (e.g. `[DISCOVERY]`, `[ARCHITECT]`, `[TESTING]`).
- **Interactive Checkpoints**: Await approval before modifying database schemas or running complex file mutations.
- **Delivery**: Claude must deliver a clean working tree. The developer holds the absolute final authority on checking in code.
