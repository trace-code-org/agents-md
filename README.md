# agents-md

Minimal file set for requirements-driven implementation.

## Files
- `requirements.md` — template/guideline for drafting `project.md` in your project
- `implementation.md` — organization-wide implementation constraints (shared)
- `instructions.md` — prompt/workflow shortcuts
- `template.md` — integration note (submodule usage)

## Usage
1. Keep this repository as `agents-md/` (for example as a git submodule).
2. If using submodules, initialize it first:
   - `git submodule update --init agents-md`
3. Maintain **project-specific requirements** in your project root using this flow:
   - Add requirement changes only as versioned delta files: `project.v2.md`, `project.v3.md`, ...
   - Consolidate the latest state into `project.md` (without version suffix)
   - Ensure the version title in `project.md` matches the highest revision
4. Treat `agents-md/implementation.md` as **organization-wide constraints** that `project.md` must satisfy.
5. In the target project, follow the root `AGENTS.md` / `agents.md` instructions for implementation flow.
