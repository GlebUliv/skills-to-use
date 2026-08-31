# SKILL: Authentication & Authorization (RBAC / BOLA) Guard

## Core Directive
Strictly prevent Broken Object Level Authorization (BOLA/IDOR), privilege escalation, missing role checks, and improper token handling in API endpoints and data access layers.

## Rules & Workflow
1. **Explicit Ownership Verification (Anti-IDOR):**
   - Never query entities solely by user-supplied identifier (e.g., `findById(req.params.id)`).
   - Always verify data ownership through authenticated tenant/user context (e.g., `findBy({ id: req.params.id, userId: req.user.id, tenantId: req.user.tenantId })`).
2. **Strict Route & Action Authorization:**
   - Every protected route, action handler, or GraphQL mutation must declare explicit permission/role gates before executing business logic.
   - Do not rely exclusively on client-side routing hides for access control; always enforce identical rules at the API layer.
3. **Token & Session Hygiene:**
   - Never store raw access/refresh tokens in unencrypted client storage (e.g., `localStorage`).
   - Use `HttpOnly`, `Secure`, `SameSite` cookies or platform-native secure keychains for token storage.
