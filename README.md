# agents-md

<img src="https://openmoji.org/data/color/svg/1F99E.svg" alt="lobster mascot" align="right" width="110" />

<sub>Mascot icon: OpenMoji (CC BY-SA 4.0)</sub>

A lightweight **requirements operating system** for AI-assisted project work.

Instead of repeating long setup prompts in every project, keep `agents-md/` as a stable submodule and evolve requirements in your project as versioned deltas.

> `agents-md` is the shared rulebook; your project owns the requirements history.

## What this is (and isn't)
- ✅ **Is:** shared process + constraints (`agents-md/`) reused across projects
- ✅ **Is:** a versioned requirements flow (`requirements/project.vN.md`)
- ❌ **Is not:** a one-off template to copy once and forget

## Files
- `requirements.md` — guideline for drafting initial project requirements (`requirements/project.v1.md`)
- `implementation.md` — organization-wide implementation constraints (shared)
- `instructions.md` — prompt/workflow shortcuts
- `template.md` — integration note (submodule usage)
- `openclaw.md` — OpenClaw extension for consistent agents-md application

## Usage
1. Keep this repository at `agents-md/` of your project
   - Recommended: pin it as a git submodule to a release branch
   - Example add command: `git submodule add -b release/v0.3 https://github.com/trace-code-org/agents-md.git agents-md`
2. Copy `agents-md/template.md` as `agents.md` into the root of you project.
3. The newly created `agents.md` file must be followd for the implementation of your project, when following the agents-md flow.
3. Maintain **project-specific requirements** as versioned delta files in `requirements/project.vN.md`
(see: `agents-md/implementation.md` → **Project Requirements / Versions**)

## Simple example prompt you can give your agent

```text
Please implement these requirements with the github.com/trace-code-org/agents-md flow:
- Build a web app that tracks naps for office cats 🐈
- Start/stop nap timer per cat
- Show daily nap leaderboard
- Add a “zoomies detected” event button
```

That’s it. Keep the request simple, and let agents-md apply its framework (requirements flow + implementation constraints).

## OpenClaw
I you are using openclaw and want to use agents-md for your projects, just tell your agent this:  
> Please copy openclaw.md of github.com/trace-code-org/agents-md into your openclaw-workspace and mention in you memory.md to strictly follow it.  

After this instruction you can allways tell you agent to create a project following the agents-md flow.  
If a project uses agents-md, he will automatically apply the flow.

## v0.3: Breaking change
Project requirement files now live in `requirements/` instead of the project root.
- Old: `project.vN.md`
- New: `requirements/project.vN.md`
