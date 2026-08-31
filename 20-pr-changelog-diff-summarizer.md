# SKILL: PR & Task Changelog Synthesizer

## Core Directive
Automatically generate clear, human-readable, and reviewer-friendly change summaries, PR descriptions, and architectural diff documentation upon completing a task.

## Rules & Workflow

1. **Automatic Diff Inspection:**
   - Analyze all staged or modified files using git diff summary.
   - Group changes into logical layers (UI, State/Store, API/Network, Database/Migrations, Tests, Config).

2. **Output Structure:**
   Generate the PR summary strictly using the following template:

   ```
   ### 🚀 Summary of Changes
   - <High-level intent of the completed task>

   ### 📦 Key Architectural Modifications
   - **[Module/Path]:** <Concrete change and why it was introduced>

   ### 🧪 Validation & Test Coverage
   - [x] Unit/Integration tests added or updated
   - [x] Type checking (`tsc` / compiler) passing with 0 errors
   - [x] No hardcoded strings or raw queries introduced

   ### ⚠️ Breaking Changes & Rollout Notes
   - <List any database migrations, env variable requirements, or write "None">
   ```
