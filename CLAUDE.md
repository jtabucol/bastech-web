[CLAUDE.md](https://github.com/user-attachments/files/27536596/CLAUDE.md)
# CLAUDE.md

This file is read by Claude (and other AI coding assistants) at the start of each session. It carries context across chats and devices so July doesn't have to re-explain things every time.

If you're a future Claude session: read this file before doing anything else in this repo. Update it (with July's approval) whenever decisions are made or context shifts.

---

## About July (universal — same in every repo)

- **Account:** GitHub `jtabucol` (https://github.com/jtabucol)
- **Works across multiple devices.** GitHub is the source of truth, not any one local machine.
- **Prefers honesty over confident guessing.** If you don't know something or a tool fails, say so plainly — never claim "from memory" what you can't actually verify.
- **Calls Claude access modes by shorthand:**
  - **"Option 1"** = GitHub MCP connector (custom connector pointing at `https://api.githubcopilot.com/mcp/`). Account-bound, persists across devices and sessions. The always-on default. Use this for browsing repos, reading deployed code, viewing commits/PRs, opening issues and PRs, pushing commits.
  - **"Option 2"** = Local clone mounted via `request_cowork_directory`. Device-bound — only works on the machine where the clone lives. Use for heavy local editing sessions. July runs `git push` herself when done. Treat as a temporary working surface, not a source of truth.
  - If July says "let's do Option 2" or "switch to Option 2," ask which device/folder, then call `request_cowork_directory`.

## Scaling plan for CLAUDE.md across repos

Currently following **Stage 1**: one CLAUDE.md per active project repo, with this universal "About July" header copied into each.

- **Stage 2 trigger:** ~10+ projects, OR the universal section grows past one page. At that point, create `jtabucol/claude-context` (private) to hold universal content centrally; each repo's CLAUDE.md shrinks to project-specific stuff plus a one-line pointer to the central repo.
- **Stage 3 trigger:** team collaborators or company growth. Move docs into a proper system (Notion/wiki); per-repo CLAUDE.md stays short and references those.

---

## About this project: bastech-web

- **What it is:** The Bastech company website.
- **Visibility:** Public.
- **Stack:** Static HTML. No build step.
- **Hosting:** Vercel. The `vercel.json` rewrites all routes to `/index.html`.
- **Entry point:** `index.html` is what Vercel serves.
- **Default branch:** `main`.

### Repo layout (as of this writing)

- `index.html` — the live, served file
- `bastech-index.html` — a working / earlier version of the page
- `bastech-index (16).html` — another snapshot (currently identical SHA to `index.html`, so this is what got promoted)
- `vercel.json` — Vercel routing config
- `CLAUDE.md` — this file

### Known gotchas / cleanup ideas

- The repo currently has multiple `bastech-index*.html` files that look like manual version snapshots. Worth consolidating into a cleaner workflow (e.g., use git history instead of duplicate files) when there's time. **Don't delete anything without asking July first.**

### Project-specific context (fill in over time)

July, this is the section to keep alive. Things worth capturing as we go:

- Goals for the site (what it should do, what success looks like)
- Brand / design decisions (fonts, colors, voice)
- Content rules (what we will / won't say)
- Deployment quirks (anything weird about the Vercel setup)
- Open todos that span sessions

---

## How to use this file (note to future Claude)

- **Read it first** when starting work on this repo.
- **Update it** when July makes a decision, when you discover something non-obvious about the codebase, or when something here turns out to be stale.
- **Keep it tight.** It's a brief, not a manual. If a section grows past a screen, that's a signal to extract it into a separate doc the file references.
- **Don't put secrets in it.** This repo is public.
