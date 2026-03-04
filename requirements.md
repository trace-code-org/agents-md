# Requirements Template (for `requirements/project.vN.md`)
This file is a **guideline/template** for creating project requirements.
It is **not** the source of truth for a concrete app.

For real projects, keep requirements as versioned delta files in `requirements/`:
- `requirements/project.vN.md`

Versioning semantics (delta behavior, ordering, and implementation interpretation) are defined in:
- `agents-md/implementation.md` → **Project Requirements / Versions**

Project requirements must be validated against `agents-md/implementation.md` before implementation.
If there are contradictions, project requirements must be adjusted to satisfy `implementation.md`.

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
