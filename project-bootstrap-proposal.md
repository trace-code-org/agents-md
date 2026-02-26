# Proposal: Streamlined Project Bootstrap Workflow

This proposal captures friction points observed while generating two demo projects end-to-end (scaffold, implement, push, publish), and suggests concrete `agents-md` improvements.

## Problem

Current workflow requires many manual hops:

- create/rename repos manually
- add submodule and copy templates manually
- write requirements from prose-only guidance
- track implementation status ad hoc
- handle git auth/protocol edge cases manually
- remember cleanup/publication steps (license, visibility, duplicate repos)

This increases time-to-first-usable-project and introduces avoidable mistakes.

## Proposed Enhancements

## 1) One-command bootstrap

Add:

```bash
agents-md init <project-name>
```

Expected behavior:

1. Create local project directory
2. Add `agents-md` (submodule or vendored template mode)
3. Copy template files into root (`project.md`, etc.)
4. Generate minimal scaffold profile (e.g. `react-ts`)
5. Initialize git and first commit
6. Optional: create GitHub repo + push

## 2) Built-in naming normalization

Add deterministic name normalization and suggestion:

- input: `Agents MD Webapp Autotest 01`
- output: `support-portal-starter`

Also provide:

```bash
agents-md rename <new-name>
```

This should rename local folder, update git remotes, and optionally rename GitHub repo.

## 3) Requirements as data + docs

Keep human-readable guidance, but add a machine-checkable schema.

- `requirements.md` (human)
- `requirements.schema.json` (machine)

Provide:

```bash
agents-md requirements lint
```

Validates count limits, forbidden sections, and required fields.

## 4) Requirement-to-implementation checklist

Auto-generate a checklist from `project.md`:

```bash
agents-md requirements status
```

Creates/updates `IMPLEMENTATION_STATUS.md` with one checkbox per requirement, including evidence pointers (files/commits).

## 5) GitHub flow helpers

Provide first-class commands:

```bash
agents-md github create
agents-md github push
agents-md github visibility public|private
agents-md github cleanup-duplicates
```

This removes repetitive `gh` and git remote operations.

## 6) Transport fallback strategy

When SSH push fails, auto-fallback to HTTPS (if authenticated via `gh`) with a clear message:

- try SSH
- on failure: run `gh auth setup-git` and retry via HTTPS

## 7) Standard baseline files

Add optional one-shot baseline:

```bash
agents-md baseline --license MIT
```

Should add at least:

- `LICENSE.md`
- `.editorconfig`
- `.gitattributes`
- README sections for run/build/test

## 8) Finalize command

One final command for publication:

```bash
agents-md finalize --push --public
```

Should:

- run checks
- commit pending changes
- push branch/main
- set visibility
- print final URLs

## Backward compatibility

All commands should be additive and optional. Existing manual workflows remain valid.

## Success criteria

- Reduce bootstrap-to-first-push time
- Eliminate manual copy/paste steps
- Fewer repo hygiene issues (duplicates, missing license, wrong visibility)
- Clear requirement coverage at any time
