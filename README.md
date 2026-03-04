# agents-md

Minimal file set for requirements-driven implementation.

## Files
- `requirements.md` — template/guideline for drafting versioned project requirements in your project (`requirements/project.vN.md`)
- `implementation.md` — organization-wide implementation constraints (shared)
- `instructions.md` — prompt/workflow shortcuts
- `template.md` — integration note (submodule usage)

## Usage
1. Keep this repository at `agents-md/`
   - Recommended: pin it as a git submodule to a release branch
   - Example add command: `git submodule add -b release/v0.3 https://github.com/trace-code-org/agents-md.git agents-md`
2. Maintain **project-specific requirements** as versioned delta files in `requirements/project.vN.md` (see: `agents-md/implementation.md` → **Project Requirements / Versions**)
3. Treat `agents-md/implementation.md` as **organization-wide constraints** that project requirements must satisfy.
4. Let the root `agents.md` in your project reference `agents-md/implementation.md`.

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
