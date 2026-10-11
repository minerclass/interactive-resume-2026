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

## 2026-10-11 - Instructional leadership merge (Claude Code + Codex drafts)

Agent: Claude Opus 5.5 (Claude Code), mac. The author asked both Claude Code and Codex
for an instructional version, reviewed both, and asked Claude Code to merge them here.
The Codex draft is commit `bb899f0` on a local, unpushed branch `instructional-leadership`
in a separate clone. That clone was read, never edited. A comparison note lives in the
author's private working notes.

### Changes

- New static companion page `docs/teaching-learning.html` (Claude Code draft):
  philosophy, practice areas, the instructional side of each role, doctoral work and
  frameworks, pedagogical writing, sessions, licensure and evaluator status. It is static
  so summarising fetches and print see the full page (see the 2026-07-22 note).
- Main page, from the Codex draft: hero title "District instructional and technology
  leader", lens 01 retargeted to instruction with new copy, an Instruction nav link, an
  "Instructional leadership" primary action, and a `#instruction` section with Codex's
  heading, lead paragraph, and four practice areas. Changed from the Codex draft:
  - the section is static HTML;
  - the one-card filters were dropped;
  - the career-direction panel became "Classroom roots / School and district
    leadership / Doctorate in progress", at the author's request. The summary carries
    one line about district leadership of teaching and learning.
- `docs/app.js`:
  - Added Phillips Achievement Academy, CPS, Lead Teacher & Social Studies Teacher,
    2006-2010.
  - District 89 title is now the official "District Instructional Technology & Social
    Studies Coordinator", per the author. Administrative scope is described in the bullets.
  - Timeline dates are now years only, because months differ between the old resume
    and LinkedIn while years agree.
  - Assistant principal bullets come from Codex and LinkedIn, plus school context: about
    870 K-5 students, 53% English learners.
  - Coach, Jefferson, and Teach Plus bullets were expanded from LinkedIn ("led" the
    REACH 2.0 project, 376-teacher survey).
  - PEL and endorsement wording replaces Type 75/09.
  - Writing changes: book renamed *EdTech Gets Schooled* (In progress); direct Social
    Studies School Service link with full title (from Codex); NSSLA *The Leader* Spring
    2024 article added; *Educational Leadership* article added with a status line.
  - `renderResources` shows an optional `status`.
- `docs/styles.css`: page-scoped `tl-` styles, plus the instruction-section styles
  adapted from the Codex draft.

### Sources and verification

- LinkedIn experience page (read in the Claude desktop browser pane) for roles, dates,
  and bullets. ISBE ELIS for licensure and evaluator dates, professional facts only.
  SSSS article page for the title, date, and C.O.R.E./H.E.A.R.T. expansions.
- *Educational Leadership*: the author supplied his 2026-10-08 submission email to the
  editorial director. Title: "The Friction Worth Protecting: Preserving Productive
  Struggle in the Age of AI". It is listed as submitted for the March 2027 issue, title
  only. The magazine asks authors not to preview articles online before publication.
- *The Leader* volume and issue (V37 N4, per a LinkedIn attachment name) are left out
  until checked against the PDF.
- Rendered in the Claude desktop browser pane at desktop width and at 375 px; console
  clean. Headless Chrome DOM dump confirmed the JS-rendered content. A Python HTML parse
  found no unclosed tags or broken in-page anchors. `app.js` parses (JavaScriptCore).

### Open items

- The "15 years directing instructional technology, curriculum, and innovation" metric
  overlaps classroom years. The author has not decided.
- The Codex clone and branch can be retired once this merge is committed.

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
