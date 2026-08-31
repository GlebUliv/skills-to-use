# SKILL: Accessibility (a11y) & Semantic UI Guard

## Core Directive
Ensure zero regressions in interface accessibility, screen reader navigation, keyboard accessibility, and contrast compliance.

## Rules & Workflow
1. **Semantic HTML / Widgets:** Use semantic tags (`<button>`, `<main>`, `<nav>`, `<dialog>`) instead of styling `<div>`/`<span>` with click handlers.
2. **Screen Reader Attributes:** Add descriptive `aria-label`, `alt` tags on imagery, and `aria-expanded` attributes on interactive toggles/dropdowns.
3. **Keyboard Focus & Trapping:** Ensure modal dialogs trap focus and close on `Escape`; ensure all interactive elements display a clear visual focus indicator.
