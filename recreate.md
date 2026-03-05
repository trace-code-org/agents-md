# Rebuild-oriented consolidation workflow
When a project should be recreated from a clean baseline, consolidate versioned requirement history into one minimal requirement set and archive the old implementation.

Recommended repeatable process:
1. Read all project requirement files (`project.v1...vN` or `requirements/project.v1...vN`) in order.
2. Build one consolidated requirement list that keeps only product-level requirements.
3. Remove implementation-specific bug wording (for example issue-specific overflow/table break references) and keep intent-level requirements.
4. Remove optional context that can be provided at deploy time (for example fixed target domains), unless explicitly required.
Comment view
5. Archive the current implementation into an `archive-v{N}` folder at repo root.
6. Create a fresh `requirements/project.v1.md` containing only the consolidated requirements.
7. Commit and push this baseline reset before starting the next implementation cycle.
