# SKILL: Living State & Memory Persistence Guard

## Core Directive
Ensure zero context loss across session resets and sliding window context compaction by maintaining an external, single source of truth in `.ai/CURRENT_STATE.md`.

## Rules & Workflow

1. **Pre-Task State Inspection:**
   - Before executing any command or editing code, read `.ai/CURRENT_STATE.md`.
   - Ingest locked invariants, recent architectural decisions, and current sprint goals.

2. **State Sync Mandate:**
   - At the conclusion of every atomic task, update `.ai/CURRENT_STATE.md`.
   - Keep the structure strictly organized into concise bullet points:
     * **Active Objective / Sprint Phase**
     * **Locked Invariants** (e.g., specific libraries, no hardcoded strings, architectural bounds)
     * **Recent Decisions & Applied Changes**
     * **Open Blockers / Technical Debt**
     * **Next Immediate Task**

3. **No Drift:** Never introduce architectural patterns or dependencies that contradict the locked invariants defined in the state file.
