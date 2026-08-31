# SKILL: Silent Failure & Observability Guard

## Core Directive
Strictly prevent silent catch blocks, swallowed errors, and blind fallback defaults that mask real failures during runtime.

## Rules & Workflow
1. **No Swallowed Exceptions:** Never write empty `catch` blocks or handlers that only do `return null`/`return false` without telemetry or debug logs.
2. **Contextual Error Wrapping:** When catching and rethrowing or handling errors, always preserve the original error stack/message and add operation metadata (IDs, params).
3. **Graceful Fallback Logging:** If a fallback default value is returned on failure, emit a structured warning log so the degradation remains observable in monitoring systems.
