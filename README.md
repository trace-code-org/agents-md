# agents-md

A lightweight **requirements operating system** for AI-assisted project work.

Instead of repeating long setup prompts in every project, keep `agents-md/` as a stable submodule and evolve requirements in your project as versioned deltas.

> `agents-md` is the shared rulebook; your project owns the requirements history.

## What this is (and isn't)
- ✅ **Is:** shared process + constraints (`agents-md/`) reused across projects
- ✅ **Is:** a versioned requirements flow (`requirements/project.vN.md`)
- ❌ **Is not:** a one-off template to copy once and forget

## Files
- `requirements.md` — guideline for drafting versioned project requirements (`requirements/project.vN.md`)
- `implementation.md` — organization-wide implementation constraints (shared)
- `instructions.md` — prompt/workflow shortcuts
- `template.md` — integration note (submodule usage)

## Usage
1. Keep this repository at `agents-md/`.
   - Recommended: pin it as a git submodule to a release branch.
   - Example: `git submodule add -b release/v0.3 https://github.com/trace-code-org/agents-md.git agents-md`
2. If using submodules, initialize it:
   - `git submodule update --init agents-md`
3. Maintain project requirements as delta files in `requirements/project.vN.md`.
4. For delta semantics and interpretation, see `agents-md/implementation.md` → **Project Requirements / Versions**.
5. Treat `agents-md/implementation.md` as organization-wide constraints your project requirements must satisfy.
6. Let the root `AGENTS.md` / `agents.md` in your project reference and follow this flow.

## Simple example prompt you can give your agent

```text
Please implement these requirements with the github.com/trace-code-org/agents-md flow:
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
