# Agent Log

Append-only record of automated and agent-assisted changes to this repository.

Purpose: this work happens from more than one machine, so local notes are not a
reliable history. Anything an agent should know about a past change belongs
here, in the repository, not in a local file.

## Conventions

- Newest entry first. Never rewrite or delete an existing entry; correct it with
  a new one that says what it supersedes.
- Record what was verified and how, not just what was edited. "Fixed" without a
  check is not a result.
- Record open items and known-failing things explicitly, so the next agent does
  not rediscover them or assume they are already handled.
- No participant data, transcripts, consent records, committee or faculty names,
  credentials, or tokens. See AGENTS.md where present.

---

## 2026-07-22 - Weekly Pages review, accessibility and CI repair

Agent: Claude Opus 4.8 (Claude Code), working from a weekly review of the
`minerclass` GitHub Pages ecosystem against recent academic and professional
activity. Author present and approving changes.

### Changes in this repository

Both changes are in `docs/app.js`, which renders the page client-side.

- Corrected the year on the *i.e.: inquiry in education* article from 2026 to
  **2025**. The journal record and the `When-Output-Looks-Like-Learning`
  companion both give Vol. 18, Iss. 1, Article 4, 2025.
- Added a missing publication: "Screen Time Is the Wrong Question: What Is the
  Screen Asking Students to Practice?", CoSN, 2026-06-23. Authorship verified on
  the CoSN page. It already had two companion sites in the ecosystem
  (`screen-time-wrong-question`, `screen-practice-compass`) but no entry here.

### Note for future agents

This page renders **everything** from `docs/app.js`. Fetching the static HTML
returns an almost empty shell, and a summarising fetch will report that the
resume has no publications, fellowships, or presentations. That is a tooling
artefact, not the page. During this review it produced a false finding that the
EDSAFE AI Vanguard Fellowship and all publications were missing; both were
already present. Inspect the rendered DOM or read `docs/app.js` directly.

The EdSurge piece that cites *unproductive success* is authored by Pattie
Morales, not by the author of this resume. It is press coverage. Do not add it
to `resources` as an authored work.

### Cross-repository context

This change set spans five repositories: `pedagogical-friction`,
`diss-proposal-defense`, `dissertationquestionsbeta`, `conference-presentations`,
and `interactive-resume-2026`. Each carries its own `AGENT_LOG.md` entry for the
same date. Check the siblings before assuming a change was isolated.
