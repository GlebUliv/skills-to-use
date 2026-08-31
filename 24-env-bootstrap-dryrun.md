# SKILL: Environment Bootstrapping & Dry-Run Guard

## Core Directive
Ensure changes never break local development onboarding, Docker builds, or require undocumented environment variables to run.

## Rules & Workflow
1. **Env Template Sync:** Whenever introducing a new environment variable in the application code, immediately update `.env.example` with a placeholder and a brief explanation comment.
2. **Build Isolation:** Verify that newly added imports or assets compile in standard environments without relying on machine-specific global binaries or untracked local files.
3. **Graceful Defaults:** Provide sensible fallback defaults for non-critical environment variables in local/development mode to prevent startup crashes.
