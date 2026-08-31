# SKILL: State & Side-Effect Safety

## Core Directive
Prevent memory leaks, race conditions, stale closures, and inconsistent application states by strictly isolating side-effects and respecting component/service lifecycles.

## Rules & Workflow

1. **State Invariance:**
   - Treat existing global state, client stores (Redux, Zustand, Pinia), and database transaction boundaries as critical invariants.
   - Do not mutate state directly outside designated state mutation pipelines/actions.

2. **Side-Effect Quarantine:**
   - Avoid injecting asynchronous or heavy side-effects into pure utility functions, computation blocks, or render phases.
   - Isolate side-effects into dedicated services, middleware, or effect hooks.

3. **Lifecycle & Resource Cleanup:**
   - Ensure all event listeners, WebSockets, background timers, intervals, and observable subscriptions include corresponding cleanup / teardown logic inside the matching lifecycle hook (e.g., `useEffect` return, `ngOnDestroy`, `dispose`).
