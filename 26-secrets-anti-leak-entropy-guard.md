# SKILL: Secrets & Sensitive Data Leak Guard

## Core Directive
Prevent committing, logging, or exposing API keys, private certificates, DB connection strings, and high-entropy secret tokens.

## Rules & Workflow
1. **Zero-Hardcoded Secrets:**
   - Prohibit inlining API keys, private keys, authorization tokens, JWT signing secrets, or connection strings in code files.
   - Always route secrets through environment configuration managers with validation (e.g., `process.env`, Doppler, Vault).
2. **Log Redaction & Masking:**
   - Prohibit logging raw request headers (especially `Authorization`, `Cookie`), passwords, credit card numbers, or full payload dumps.
   - Implement explicit masking/sanitization on loggers before sending telemetry to external monitoring.
3. **Pre-Commit Entropy Check:**
   - Before finishing any task, perform a self-audit of modified files to ensure no sensitive test credentials or environment dumps remain.
