# SKILL: Atomic Session Handoff & Compaction Protocol

## Core Directive
Maintain deterministic continuity across new chat sessions and context resets by generating standardized handoff checkpoints.

## Rules & Workflow

1. **Atomic Completion Gate:**
   - Once a task is completed, verified, and passes tests/types:
     * Stage changes with clean commit messages.
     * Update `.ai/CURRENT_STATE.md`.
     * Provide a standardized **Session Handoff Summary**.

2. **Handoff Output Format:**
   ```
   ### 🔄 Clean Session Handoff Checkpoint
   - **Completed:** <Summary of merged/verified changes>
   - **Verified By:** [Tests Passing | Linter Clean | Type Check Passed]
   - **Current Repo State:** Clean / Ready for next thread
   - **Recommended Next Prompt:** <Exact copy-pasteable prompt for the new chat session>
   ```

3. **New Session Ingestion:**
   - When starting a new session, the agent's first action is to read the latest handoff summary and `.ai/CURRENT_STATE.md` to resume without history drift.
