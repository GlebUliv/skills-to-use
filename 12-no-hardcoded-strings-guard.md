# SKILL: No-Hardcoded-Text & Centralized String Guard

## Core Directive
Strictly prohibit hardcoding any user-facing strings, UI labels, error messages, toast notifications, button texts, placeholders, or modal descriptions directly in components, templates, or business logic. All strings must be extracted into centralized constants, dictionaries, localization keys (i18n/l10n), or configuration files—even if the project currently supports only a single language.

## Rules & Execution Workflow

### 1. Zero-Hardcoding Mandate
- Never render raw text strings inside UI components (e.g., JSX/TSX text nodes, HTML templates, Flutter `Text('...')`, Swift/Kotlin UI views).
- Never inline raw user-facing messages inside exceptions, alerts, form validators, or toast triggers.

### 2. Centralized Source of Truth
- **Existing i18n/l10n setup:** Look up the established localization dictionary/JSON/hook (e.g., `react-i18next`, `next-intl`, Flutter `.arb`, Android `strings.xml`, iOS `Localizable.strings`) and add new keys matching the existing naming convention (e.g., `auth.errors.invalid_email`, `common.buttons.save`).
- **Single-language / No i18n setup:** Place strings into a dedicated constants/strings file (e.g., `src/constants/strings.ts` or module-level `feature.constants.ts`) using descriptive key hierarchies:
  ```ts
  export const STRINGS = {
    AUTH: {
      LOGIN_BUTTON: 'Sign In',
      EMAIL_PLACEHOLDER: 'Enter your email',
    },
  } as const;
  ```

### 3. Dynamic Values & Interpolation
- Never assemble user-facing sentences via raw string concatenation (e.g., `'Items left: ' + count`).
- Use structured interpolation templates or parameterized formatters:
  * i18n: `t('items_left', { count })`
  * String constants: `STRINGS.ITEMS_LEFT(count)` or template functions.

### 4. Code Review Gate
Before finalizing any task, scan all modified files:
- If a hardcoded user-visible string is found $ightarrow$ extract it to the centralized repository and replace it with the variable reference.
