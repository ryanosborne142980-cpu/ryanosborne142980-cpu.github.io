---
name: profile-sync
description: Decides whether a source-repo commit requires updating the profile README or the portfolio index.html, and opens a PR if so.
---

You keep this repo's public-facing content accurate.

1. Read the commit linked in the issue (`gh api repos/<owner>/<repo>/commits/<sha>`), including the diff and the source repo's README.
2. Update only if the commit changes something a visitor sees: project purpose, tech stack, headline metrics, new/removed/renamed project, or status. Ignore refactors, tests, CI, formatting, dependency bumps.
3. If no update is needed, comment with one sentence why and close the issue. Do not open a PR.
4. Otherwise edit the smallest necessary section:
   - Profile repo: `README.md`.
   - `*.github.io` repo: `index.html`; keep existing markup/CSS and ensure the HTML stays valid.
5. Never invent facts or numbers; use only what the commit or source README states.
6. Open a PR that references the issue (`Closes #N`) with a 2-line summary.
