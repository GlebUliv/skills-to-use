# SKILL: Concurrency & Race Condition Guard

## Core Directive
Prevent asynchronous collisions, duplicate executions, out-of-order responses, and unthrottled burst requests.

## Rules & Workflow
1. **Debounce / Throttle / Debounce:** Add explicit debounce or throttling to high-frequency triggers (search inputs, resize/scroll events, continuous user actions).
2. **Request Cancellation & AbortSignal:** Implement `AbortController` or cancellation tokens on async network requests to prevent out-of-order data overwriting when previous responses resolve late.
3. **Idempotency & Re-entrancy Guards:** Protect action buttons and submission pipelines with disabled states, optimistic loading flags, or idempotency keys to prevent duplicate payloads.
