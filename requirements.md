# Requirements Template (for `project.vN.md`)
This file is a **guideline/template** for creating project requirements.
It is **not** the source of truth for a concrete app.

For real projects, keep requirements in the project root:
- `project.vN.md` files are the source of truth
- each new version captures the requirement delta from the previous version
- the highest `project.vN.md` is the latest requirement state for implementation

### Relation between `project.vN.md` and `agents-md/implementation.md`
Project requirements must be validated against `agents-md/implementation.md` before implementation.
If there are contradictions, project requirements must be adjusted to satisfy `implementation.md`.

### Versioning (mandatory)
When requirements change, the implementation flow must follow this sequence:

1. Create a new revision file: `project.v{N+1}.md` (delta from previous version).
2. Ensure the new revision keeps all active requirements that still apply (do not silently drop scope).
3. Implement code changes according to the highest `project.vN.md` together with prior revisions.

Do not skip step (1) when requirement scope/behavior changes.

### Human-in-the-loop (HITL)
If requirements are added/edited by a human, the agent should create/update the next `project.v{N+1}.md` and then implement accordingly.

## Prompt Template
> Can you please generate some example-requirements for an application?
> The requirements should be kind of specific (not to generic).
> 
> ### Base Requirements
>  - Only web-applications for frontend. No native apps.
>  - The system shall be usable on modern desktop and/or mobile browsers.
> 
> ### Restrictions
>  - not more than 10 functional requirements (base requirements excluded)
> - no non-functional requirements
