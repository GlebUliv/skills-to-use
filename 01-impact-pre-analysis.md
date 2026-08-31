# SKILL: Impact & Regression Pre-Analysis Guard

## Core Directive
You are strictly forbidden from writing code, modifying files, or applying diffs on the initial step of a new task. Before any code generation begins, you must perform a comprehensive "Blast Radius & Regression Analysis" to ensure changes requested in the prompt do not degrade or break existing functionality.

## Execution Workflow

### Step 1: Request & Context Ingestion
- Read the incoming task prompt completely.
- Map the target scope (which files/functions are explicitly mentioned vs. implicitly affected).

### Step 2: Codebase Dependency & Impact Mapping
- Inspect current working code, call hierarchies, public interfaces, types/schemas, state management, and tests.
- Identify potential breaking changes:
  * Signature/API contract mutations.
  * Shared state or side-effect collisions.
  * Architectural patterns and hidden invariants.
  * Impact on existing test suites or consumer modules.

### Step 3: Impact Evaluation & Report Gate
Produce a structured Impact Report directly to the user before making any code modifications.

Format the output strictly as follows:

```
### 🔍 Impact & Blast Radius Analysis
- **Task Objective:** <Summary of target goal>
- **Target & Dependent Modules:** <Files, interfaces, and consumers involved>
- **Risk Level:** [Low | Medium | High | Critical]

### ⚠️ Potential Breakages & Side Effects
- <Concrete failure modes if implemented naively, or "None detected" if safe>

### 🛠️ Minimal-Blast Implementation Strategy
- **Least-Disruptive Approach:** <How to fulfill task while preserving existing features>
- **Action Plan:** <Target files and exact functional modifications>
- **Trade-offs:** <Any technical debt vs cleaner refactoring considerations>
```

### Step 4: Execution Criteria
- If **Risk Level is Low / Safe**: Present minimal-impact plan and proceed.
- If **Risk Level is Medium / High / Critical**: HALT immediately after the report. Do NOT execute tool edits or apply diffs until the user explicitly approves the approach.
