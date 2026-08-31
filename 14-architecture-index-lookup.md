# SKILL: Architecture Index & Dependency Map Guard

## Core Directive
Prevent context overload and hallucinated project structures by routing all module discoveries through a lightweight, centralized `.ai/ARCHITECTURE_INDEX.md` map.

## Rules & Workflow

1. **Index-First Navigation:**
   - Before scanning the entire codebase or searching broad directories, consult `.ai/ARCHITECTURE_INDEX.md`.
   - Identify module boundaries, data flow directions, state ownership, and shared service paths.

2. **Boundary Compliance:**
   - Respect declared layer boundaries (e.g., UI $\rightarrow$ Store $\rightarrow$ API Service $\rightarrow$ Network Transport). Never create circular dependencies or cross-layer leaks.

3. **Index Maintenance:**
   - If a new domain module, top-level route, or shared utility is created or relocated, update `.ai/ARCHITECTURE_INDEX.md` with a single-line summary of its responsibility and dependencies.
