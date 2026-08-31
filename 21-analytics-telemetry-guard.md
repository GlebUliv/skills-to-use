# SKILL: Product Analytics & Telemetry Guard

## Core Directive
Ensure all critical user actions, conversion funnels, lifecycle milestones, and error occurrences are accurately tracked with consistent naming schemas without leaking PII (Personally Identifiable Information).

## Rules & Workflow
1. **Event Completeness:** Whenever adding or altering interactive flows (buttons, forms, modals, checkouts), verify that matching tracking events exist (e.g., `trackEvent('button_clicked', { button_id: 'submit_order' })`).
2. **Naming Convention:** Strictly follow the project taxonomy (e.g., snake_case vs PascalCase: `feature_name:action_performed`). Never invent unstandardized event names.
3. **PII Sanitization:** Never pass raw emails, phone numbers, full names, or auth tokens inside event properties or tracking payloads.
