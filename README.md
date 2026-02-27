# agents-md

Minimal docs scaffold for requirement-driven project generation.

## Files

- `requirements.md` — project requirements format + constraints
- `implementation.md` — organization-level implementation rules
- `instructions.md` — prompts/workflow for initial and follow-up implementation
- `template.md` — setup template snippet for repositories using this scaffold

## Setup (before implementation)

1. Copy these files into your project root (or add this repo as `agents-md/`).
2. If using as submodule, initialize it:
   - `git submodule update --init --recursive agents-md`
3. Confirm these files exist and are up to date:
   - `requirements.md`
   - `implementation.md`
   - `instructions.md`
4. Start implementation with the prompt from `instructions.md`.

## Default prompts

- Initial: `Please implement this project`
- Follow-up: `Please implement new requirements`
