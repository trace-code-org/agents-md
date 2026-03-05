# agents-md

Minimal file set for requirements-driven implementation.

## Files
- `requirements.md` — template/guideline for drafting versioned project requirements in your project (`requirements/project.vN.md`)
- `implementation.md` — organization-wide implementation constraints (shared)
- `instructions.md` — prompt/workflow shortcuts
- `template.md` — integration note (submodule usage)

## Usage
1. Keep this repository at `agents-md/` (using it as git submodule is recommended)
   - Recommended: pin the submodule to a release branch (for example `release/v0.1`) so breaking changes from `main` are not pulled automatically.
   - Example add command: `git submodule add -b release/v0.1 https://github.com/trace-code-org/agents-md.git agents-md`
2. If using submodules, initialize it first:
   - `git submodule update --init agents-md`
3. Maintain **project-specific requirements** as versioned delta files in `requirements/`: `requirements/project.v1.md`, `requirements/project.v2.md`, `requirements/project.v3.md`, ...
4. For versioning rules and how deltas are interpreted, see `agents-md/implementation.md` → **Project Requirements / Versions**.
5. Before any implementation behavior/UI/API change, add a new requirement delta file (`requirements/project.v{N+1}.md`) describing the change.
6. Treat `agents-md/implementation.md` as **organization-wide constraints** that project requirements must satisfy.
7. In the target project, follow the root `AGENTS.md` / `agents.md` instructions for implementation flow.

## Simple example prompt you can give your agent

```text
Please implement these requirements with the agents-md flow:
- Build a web app that tracks naps for office cats 🐈
- Start/stop nap timer per cat
- Show daily nap leaderboard
- Add a “zoomies detected” event button
```

That’s it. Keep the request simple, and let agents-md apply its framework (requirements flow + implementation constraints).

## v0.3: Breaking change
Project requirement files now live in `requirements/` instead of the project root.
- Old: `project.vN.md`
- New: `requirements/project.vN.md`
