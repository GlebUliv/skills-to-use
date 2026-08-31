# SKILL: Rate Limiting & Resource Exhaustion (DoS) Defense

## Core Directive
Protect APIs, compute resources, and memory pools against denial-of-service, unconstrained memory allocation, and brute-force abuse.

## Rules & Workflow
1. **Unbounded Query & Pagination Caps:**
   - Never allow unpaginated collection queries. Enforce hard server-side maximum limits (e.g., `limit = Math.min(requestedLimit || 20, 100)`).
2. **Payload & File Upload Boundaries:**
   - Enforce strict size limits on incoming JSON payloads and multipart file uploads at the middleware/gateway level.
   - Validate file MIME types using magic bytes (header inspection), not untrusted client file extensions.
3. **Brute-Force & Rate Limiting Hooks:**
   - Add rate-limiting throttles on sensitive endpoints: login, password reset, OTP verification, and high-cost AI/generation pipelines.
