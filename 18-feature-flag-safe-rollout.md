# SKILL: Feature Flag & Progressive Rollout Guard

## Core Directive
Isolate new, experimental, or major workflow changes behind conditional runtime feature flags or toggle guards to ensure effortless rollback and zero blast radius in production.

## Rules & Workflow

1. **Feature Flag Wrapping:**
   - Wrap high-risk logic, alternative UI flows, and new integration adapters behind a project-standard feature flag checker (e.g., `featureFlags.isEnabled('FEATURE_KEY')`).
   - Provide clean, deterministic fallback branches preserving the previous stable behavior when the flag is disabled.

2. **Clean Separation:**
   - Avoid interleaving new experimental code directly into legacy functions. Use strategy patterns, branch switches, or adapter dispatchers to isolate the new path.

3. **Deprecation & Cleanup Path:**
   - Document the feature flag name and expected sunset criteria directly in the code comments or task tracking file to facilitate easy deletion after full rollout.
