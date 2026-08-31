# SKILL: Silent Regression Forensics & Deep Root-Cause Analysis

## Trigger Condition
Activate this protocol immediately when a feature or behavior is broken, degraded, or inconsistent, but automated test suites, linters, and type-checkers report green/passing status.

## Investigation Workflow

### Step 1: Git Diff & Temporal Blast Radius
- Inspect recent commits or modified diff (`git diff HEAD~1` or touched file list).
- Identify changes outside tested paths:
  * Default argument shifts and optional parameter fallbacks.
  * Async execution order, unhandled promises, or missing `await`.
  * Lifecycle mount/unmount triggers and event subscription teardowns.
  * Cache keys, memoization dependencies (`useMemo`, `useCallback`, computed props).

### Step 2: Test Blindspot Audit
- Locate covering tests and identify why they failed to catch the regression:
  * **Over-mocking:** Stale mock payloads hiding runtime contract changes.
  * **Assertion Weakness:** Shallow checks (e.g., status 200 instead of body structure).
  * **Async Gaps:** Tests finishing synchronously before downstream event loops complete.
  * **Missing Edge States:** Uncovered reconnects, empty states, or timeout handlers.

### Step 3: Forensic Diagnostic Matrix
Output this structured report before touching code:

```
### 🕵️ Silent Regression Investigation Report
- **Observed Bug vs Expected:** <Clear breakdown of symptom>
- **The "Silent" Root Cause:** <Exact code line/runtime logic failure point>
- **Test Blindspot:** <Why automated tests/types stayed green despite bug>
- **Mechanics of Failure:** [State Race | Cache Invalidation | Serialization/Type Drift | Lifecycle Leak | Stale Mock]

### 🧪 Proof-of-Bug (Reproduction Target)
- <Minimal assertion or reproduction steps failing on current code>

### 🩹 Two-Part Fix Strategy
1. **Surgical Fix:** <Minimal-blast patch to resolve runtime issue>
2. **Test Patch:** <Concrete test update to close blindspot permanently>
```

### Step 4: Resolution Rules
1. Formulate the failing reproduction assertion first.
2. Apply the minimal surgical fix.
3. Update/add the regression test to ensure it never passes CI silently again.
