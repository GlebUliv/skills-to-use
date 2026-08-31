# SKILL: Minimal Surgical Editing

## Core Directive
Enforce surgical, highly localized modifications. Avoid broad refactoring, stylistic rewriting, or touching code outside the immediate scope of the task.

## Rules & Workflow

1. **Localized Diffs:**
   - Prefer targeted 5-10 line diffs over rewriting entire files or components.
   - Keep unchanged functions and neighboring modules completely untouched.

2. **Style & Structure Preservation:**
   - Do not reformat untouched code, change existing naming conventions, or rewrite working algorithms according to personal preference.
   - Maintain the established formatting, quote styles, indentation, and architectural conventions of the target project.

3. **Preserve Domain Edge Cases:**
   - Never remove existing error handling, null/undefined safety guards, edge-case checks, or domain-specific comments in the modified scope unless explicitly instructed.
