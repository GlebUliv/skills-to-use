# SKILL: Security & Injection Defense

## Core Directive
Ensure zero vulnerabilities related to unsanitized inputs, raw queries, unsafe DOM injections, and unauthorized data exposure.

## Rules & Workflow
1. **No Raw Query Concatenation:** Always enforce parameterized queries, ORM query builders, or prepared statements. Never concatenate untrusted strings into SQL/NoSQL filters.
2. **Sanitize Dynamic Renders:** Avoid raw HTML injections (`dangerouslySetInnerHTML`, `v-html`, `innerHTML`) unless passing through a verified sanitizer (e.g., DOMPurify).
3. **Data Exposure & Serialization:** Strip sensitive credentials, hashed passwords, internal tokens, and private metadata before serializing objects into client-facing responses.
