# CLAUDE.md — PM Prep Hub

## Purpose
Interview preparation site for Liubov Vassilevskaya, targeting a Senior/Staff-level PM role. Two overlapping tracks live in this one file:
1. **General track** — "AI-native growth-oriented consumer wellness PM with founder experience" narrative, built around her own product **FemFast** (an AI cycle-tracking / hormonal health app she built to 300+ paying users, 24.6% paid conversion).
2. **Specific track** — a real **Samsung Food GPM** requisition (Group Product Manager, Samsung Health HQ Korea, leading 3 direct-report PMs, distributed team across 30+ countries). The Management Q&A and PM Documents sections are written specifically for this req, not the general track.

These two tracks are not currently labeled or separated at the nav level — a candidate should know which questions belong to which track before a real interview. Worth reconciling in a future session (see Known Gaps below).

## Critical rule — do not put children's content here
This repo is **public** and tied to Liubov's real name for job-search purposes. **Never add anything related to her children here** — no names, no folders, no files, no links. Kids' learning content belongs exclusively in separate, dedicated repos (see her `liubov-context` repo's infrastructure notes for details — not reproduced here on purpose, since this file is itself public).

This repo previously had a folder with a child's page added by mistake, on two separate occasions. Both were fully removed from the live site **and** scrubbed from git history via rebase/force-push. Do not reintroduce this pattern even if asked to follow "the existing convention" — there isn't one anymore, deliberately. This note itself is deliberately vague about details, since specifics belong in a private repo, not a public one.

## Structure
Single self-contained `index.html` (~230KB). No external local assets — only Google Fonts and a handful of external `<a>` links to genuinely stable domains (a16z.com/ai, oneusefulthing.org, nngroup.com, rockhealth.com, fda.gov, anthropic.com, simonwillison.net, latent.space, lennysnewsletter.com). Navigation is JS-driven show/hide (`show(id)` function toggles `.active` class), **not** anchor-scroll — different from the kids' pages, which use real in-page anchor scrolling. Don't confuse the two patterns when editing either.

### Current sections (in nav order)
`dashboard` · `daily` · `plan` (30-Day Plan) · `stories` (Story Library) · `frameworks` · `metrics` · `aitrends` · `staffpm` (Staff PM Strategy) · `whjudgment` (Women's Health Product Judgment) · `aiskills` (AI & Future of PM) · `casestudies` · `questions` (Question Bank) · `positioning` · `reflection` (Weekly Reflection) · `prd` (PRD Mastery) · `devprocess` (Agile/Sprints) · `mgmtqa` (Management Q&A — Samsung Food specific) · `pmdocs` (PM Documents) · `files` (Prep Files)

### Content patterns to reuse when adding a new section
- Header: `<div class="ph"><h2>Title</h2><p>subtitle</p></div>`
- Topic grid: `.trend2` (2-col grid) of `.tbox` cards, each `<h4>` + `<ul class="tlist">`
- Callout: `.alert-amber` for a highlighted note/practice question
- Resource list: plain `<div>` rows with `→ <a href="..." target="_blank">Name</a> — description`
- Detailed doc-style content (PRD Mastery, Dev Process): `.card` with `.card-t` title, tables, and color-coded left-border boxes
- **Link discipline:** only hyperlink domains you're highly confident are stable and real. For a specific case/article you can't verify a URL for, describe it in plain text ("search for X") rather than guessing a deep link.

### Data-driven sections (content lives in JS arrays, not static HTML)
- `stories` array — 17 STAR stories, 9 fields each. **Stories 11–17 are stubs** (title + one-line hint only, no full scenario) — flagged honestly by the Dashboard's "1/17 built" stat. Filling these in is the single most valuable next step for interview readiness.
- `fw` array — 18 frameworks across 4 categories, all fully fleshed out (desc, FemFast application, common mistake, resource link).
- `cs` / `csQ` — Case Studies: Flo, Clue, Zero, Noom, Calm, Duolingo, Notion, Headspace, OpenAI, each with 6 blank textareas. **Intentionally empty** — this is a practice space for Liubov to fill in herself, not content to generate on her behalf.
- `mqaData` — Management Q&A, Samsung Food GPM specific, with model answers already written.
- `pmDocs` — 9 PM document types (PRD, A/B Test Brief, Design Brief, etc.) with Samsung Food worked examples.

### Persistence
`localStorage` keys prefixed `pm2_` (e.g. `pm2_<textarea-id>`, `pm2_cb_<checkbox-id>`). Progress bar on the sidebar (`#prog-fill`, `#prog-txt`) is computed from checkbox completion across the 30-Day Plan.

## Deployment
- Repo: `Liubov-personal-use/pm-prep-hub` (public), GitHub Pages serving from `main` branch root.
- Live at: **https://liubov-personal-use.github.io/pm-prep-hub/**
- There is also a local working copy at `~/Desktop/Claude Folder/Career/Intervie Prep/Liubov's PM Career Preparation/PM_Prep_Hub.html` — historically edited in parallel with this repo. Treat **this repo as canonical** going forward; if the Desktop copy and the repo ever diverge, the repo (what's actually live) wins, and the Desktop copy should be resynced from it.
- Standard flow: edit `index.html` directly in a clone of this repo → commit → push to `main`. No staging branch or build step — it's plain static HTML, pushed straight to production.

## Known gaps (candidates for a future session)
1. Stories 11–17 are stubs — need full 9-field write-ups.
2. Case Studies textareas are empty — Liubov's own analysis, not to be pre-filled by an agent.
3. General track vs. Samsung Food GPM track aren't visually distinguished in the nav — a future pass could tag nav items or split into two modes so it's obvious which prep applies to which interview.
