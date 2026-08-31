# SKILL: Performance, Allocation & Re-render Guard

## Core Directive
Prevent performance regressions, memory thrashing, unnecessary component re-renders, and inefficient algorithmic bottlenecks ($O(N^2)$ loops, repeated lookups, or unindexed object scanning).

## Rules & Workflow

1. **Rendering & Computation Memoization:**
   - Wrap expensive computation / data-transform loops in appropriate memoization utilities (`useMemo`, computed properties, selectors).
   - Ensure event handler callbacks passed down to memoized list children or heavy sub-trees use stable references (`useCallback`, bound actions).

2. **Collection Lookup Optimization:**
   - Prohibit repeated `.find()`, `.filter()`, or `.some()` calls inside loops or high-frequency render passes.
   - Index collections into a `Map` or `Set` lookup structure before iterating.

3. **Asset & Memory Footprint:**
   - Enforce pagination, virtualization, or infinite scroll on lists that render dynamic items of arbitrary size.
   - Avoid creating large temporary object arrays inside animation frames, canvas render loops, or high-frequency stream events.
