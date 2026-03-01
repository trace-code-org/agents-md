# Instructions
These instructions are meant as prompts for maximum reproducability.

**initial implementation**: `Please implement this project`  
**implementation of additional requirements:** `Please implement new requirements`

## Requirements versioning (mandatory)
When requirements change, the implementation flow must follow this sequence:

1. Create a new revision file: `project.v{N+1}.md` (delta from previous version).
2. Update `project.md` so it contains the consolidated latest requirements.
3. Ensure the version title in `project.md` matches the highest revision (e.g. `Project Requirements v3`).
4. Implement code changes according to the resulting `project.md`.

Do not skip step (1) when requirement scope/behavior changes.