# SKILL: SSRF & File Path Traversal Defense

## Core Directive
Prevent Server-Side Request Forgery (SSRF), arbitrary file reads, path traversal attacks, and unsafe local resource access from user-controlled inputs.

## Rules & Workflow
1. **Path Traversal Mitigation:**
   - Never construct file system paths via raw string interpolation with user input (e.g., `path.join('/uploads', userFileName)`).
   - Sanitize file paths, resolve them against an allowed root directory, and verify with `resolvedPath.startsWith(ALLOWED_ROOT)`.
   - Never allow `../` sequences to escape target sandbox directories.
2. **SSRF Quarantine:**
   - When fetching URLs provided by users (e.g., webhooks, avatar URLs), validate domains against an allowlist.
   - Block requests targeting internal loopbacks (`127.0.0.1`, `localhost`), private subnets (`10.0.0.0/8`, `192.168.0.0/16`, `172.16.0.0/12`), and cloud metadata IP endpoints (`169.254.169.254`).
