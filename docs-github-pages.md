# Proposal: GitHub Pages for agents-md

This PR adds a minimal static landing page to make `agents-md` easier to discover and use.

## What is included

- `site/index.html` — simple static page with:
  - project intro
  - links to repository and docs
  - suggested command flow

## Suggested enablement

In repository settings:

- **Pages source:** `Deploy from a branch`
- **Branch:** `main`
- **Folder:** `/site`

This keeps hosting simple and avoids extra build tooling.

## Why

- Better first impression for newcomers
- Quick copy/paste commands for setup
- No dependency on static site generators
