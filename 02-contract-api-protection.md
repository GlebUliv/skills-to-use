# SKILL: Public Contract & Signature Immutability

## Core Directive
Preserve all public contracts, type definitions, schemas, and API signatures to prevent cascading breakages across dependent modules, services, or frontends.

## Rules & Workflow

1. **Signature Immutability:**
   - Never rename, remove, or alter the parameter order or types of exported functions, public API endpoints, or shared database schemas.
   - If new requirements require extra parameters, make them optional (`param?: Type` / default values) or introduce overload/adapter patterns.

2. **Backward Compatibility:**
   - Do not remove or rename fields in DTOs, response bodies, or shared event interfaces.
   - Maintain legacy behavior alongside new logic using non-breaking additive extensions.

3. **Breaking Change Protocol:**
   - If modifying an existing contract is unavoidable:
     * Perform a full-text reference search across the entire codebase to list every consumer.
     * Present a deprecation notice and explicit migration plan for review before making any edits.
