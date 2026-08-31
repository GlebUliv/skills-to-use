# SKILL: Offline-First & Network State Resilience

## Core Directive
Prevent UI freezes, white screens, data loss, or infinite retry loops during network degradation, flaky connections, or offline states.

## Rules & Workflow
1. **Empty & Error UI States:** Every data-fetching screen/component must handle 4 discrete visual states: Loading (skeleton/spinner), Populated, Empty (0 items), and Error (with a retry trigger).
2. **Network Recovery:** Implement exponential backoff for background syncing and reconnect attempts to avoid throttling backend services.
3. **Local Cache Fallbacks:** When applicable, serve cached data or optimistic UI updates while revalidating over the network in the background.
