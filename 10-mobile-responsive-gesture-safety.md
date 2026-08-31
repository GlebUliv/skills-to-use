# SKILL: Mobile & Responsive Layout Guard

## Core Directive
Prevent visual clipping, keyboard overlap, touch gesture conflicts, and unresponsive viewports across various screen dimensions.

## Rules & Workflow
1. **Safe Area & Viewport Insets:** Always respect notch, home indicator, and software keyboard boundaries using safe area insets / keyboard avoidance wrappers.
2. **Touch Targets & Gestures:** Ensure interactive elements maintain minimum touch target dimensions (at least 44x44 / 48x48 pt) and do not conflict with parent swipe/drag gestures.
3. **Overflow & Wrapping:** Protect layout containers with flexible wrapping and truncation rules to prevent horizontal overflow and broken typography on narrow screens.
