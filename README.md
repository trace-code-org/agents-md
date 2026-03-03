# agents-md

Minimal file set for requirements-driven implementation.

## Files
- `requirements.md` — template/guideline for drafting `project.md` in your project
- `implementation.md` — organization-wide implementation constraints (shared)
- `instructions.md` — prompt/workflow shortcuts
- `template.md` — integration note (submodule usage)

## Usage
1. Keep this repository at `agents-md/` (using it as git submodule is recommended)
2. If using submodules, initialize it first:
   - `git submodule update --init agents-md`
3. Maintain **project-specific requirements** in your project root using this flow:
   - Add requirement changes only as versioned delta files: `project.v2.md`, `project.v3.md`, ...
   - Consolidate the latest state into `project.md` (without version suffix)
   - Ensure the version title in `project.md` matches the highest revision
4. Treat `agents-md/implementation.md` as **organization-wide constraints** that `project.md` must satisfy.
5. In the target project, follow the root `AGENTS.md` / `agents.md` instructions for implementation flow.

## Example: ordering your agent to implement with agents-md

Use a concrete instruction that forces the requirements flow:

```text
Implement a web app with agents-md.

Requirements workflow (mandatory):
1) Add requirement changes as `project.vN.md` (start at v1 if missing)
2) Consolidate latest state into `project.md`
3) Validate `project.md` against `agents-md/implementation.md`
4) Implement only what matches the consolidated requirements
5) If requirements change, create next `project.vN.md`, then re-consolidate `project.md`

Delivery:
- Keep code readable/maintainable
- Commit with clear messages
- Open a PR summarizing requirement versions touched and implementation changes
```

This pattern helps prevent drift between what was requested and what was implemented.
