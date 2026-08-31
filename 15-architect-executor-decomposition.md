# SKILL: Two-Phase Task Decomposition (Architect & Executor)

## Core Directive
Strictly decouple planning and system design from code execution for multi-file or complex tasks to eliminate cognitive drift and tunnel-vision bugs.

## Rules & Workflow

1. **Phase 1 (Architect Mode):**
   - When receiving a complex prompt, generate a structured implementation plan inside `.ai/TASKS/task-[id]-plan.md`.
   - Detail the exact files, interface changes, data flows, and edge cases.
   - **Do not modify source code in Phase 1.**

2. **Phase 2 (Executor Mode):**
   - Read the approved task plan from `.ai/TASKS/task-[id]-plan.md`.
   - Implement the changes sequentially in small, verifiable steps.
   - Mark off completed checkpoints in the task plan document.

3. **Scope Enclosure:**
   - Never implement features, refactors, or fixes that are outside the scope of the active step in the task plan.
