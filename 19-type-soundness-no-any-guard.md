# SKILL: Strict Type Soundness & Anti-Any Guard

## Core Directive
Enforce strict type soundness. Strictly prohibit the use of `any`, unsafe type casts, and suppressive type assertions that bypass compiler safety guarantees.

## Rules & Workflow

1. **Zero `any` Tolerance:**
   - Never introduce `any`, `Object`, or untyped definitions for variables, function arguments, or return types.
   - Use `unknown` with runtime type narrowing / type guards (e.g., `typeof`, `instanceof`, Zod/Valibot schemas) when handling untrusted or dynamic data.

2. **Safe Type Narrowing vs Force Casts:**
   - Avoid aggressive type assertions (e.g., `as unknown as TargetType`, `as any`, non-null assertions `!`) unless mathematically proven impossible to fail and accompanied by an explanatory inline comment.

3. **Generic & Utility Types:**
   - Leverage native utility types (`Readonly`, `Partial`, `Pick`, `Record`, `Extract`) to construct resilient, expressive contracts without type duplication.
