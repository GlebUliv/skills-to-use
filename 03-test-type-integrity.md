# SKILL: Test & Type Integrity Guard

## Core Directive
Ensure zero regressions by validating existing test suites, compiler constraints, and static analyzers before, during, and after implementing changes.

## Rules & Workflow

1. **Pre-Execution Baseline:**
   - Locate test suites covering the target area and inspect current assertions.
   - Verify existing compiler/linter state before making modifications.

2. **Test-First Bug Reproduction:**
   - For bugfixes or new feature branches: write or identify a minimal failing test case that reproduces the issue or asserts new behavior prior to modifying core logic.

3. **Post-Execution Verification Mandate:**
   - Run type-checkers (e.g., `tsc --noEmit`, `mypy`, `cargo check`, `go build`).
   - Run linters and project test suites for all affected modules.
   - Never mark a task complete or consider code ready if type errors, linter violations, or broken test assertions remain.
