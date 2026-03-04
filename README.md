# agents-md

Minimal file set for requirements-driven implementation.

## Files
- `requirements.md` — template/guideline for drafting versioned project requirements in your project (`project.vN.md`)
- `implementation.md` — organization-wide implementation constraints (shared)
- `instructions.md` — prompt/workflow shortcuts
- `template.md` — integration note (submodule usage)

## Usage
1. Keep this repository at `agents-md/` (using it as git submodule is recommended)
2. If using submodules, initialize it first:
   - `git submodule update --init agents-md`
3. Maintain **project-specific requirements** in your project root using this flow:
   - Keep requirements in versioned files only: `project.v1.md`, `project.v2.md`, `project.v3.md`, ...
   - Each new revision should represent the requirement delta from the previous revision
   - The highest `project.vN.md` is the canonical latest requirement state for implementation
4. Treat `agents-md/implementation.md` as **organization-wide constraints** that `project.vN.md` requirements must satisfy.
5. In the target project, follow the root `AGENTS.md` / `agents.md` instructions for implementation flow.

## Simple example prompt you can give your agent

```text
Please implement these requirements with the agents-md flow:
- Build a web app that tracks naps for office cats 🐈
- Start/stop nap timer per cat
- Show daily nap leaderboard
- Add a “zoomies detected” event button
```

That’s it. Keep the request simple, and let agents-md apply its framework (requirements flow + implementation constraints).
