# Skill backlog

Prioritized candidates for growing this library, surveyed 2026-07-02. Every
candidate must generalize across the whole way of working — solo, natural-language
prompting, multi-repo (varying maturity), git/GitHub branch-and-PR, local Claude
Code and Claude Code web (ephemeral containers) — and nothing codebase- or
domain-specific belongs here.

## Tier 1 — build first (compound value or protect against real loss)

1. **skill-authoring** — Meta-skill encoding this library's own format, trigger
   style, and quality bar, so every future skill comes out consistent; it's the
   skill that makes the library self-growing.
2. **ephemeral-session-hygiene** — Commit-and-push cadence rules for web sessions
   (branch immediately, push WIP early, never end a turn with unpushed work);
   ephemeral containers are the one place this workflow can silently lose hours.
3. **verification-standards** — What "done" means before Claude reports success
   (run the actual thing, show evidence; passing tests alone don't count);
   critical when the user reviews outcomes, not code.
4. **pr-authoring** — House style for PRs: size limits, description structure,
   self-review pass, draft vs ready; the PR is the solo user's main review
   surface, so its quality gates everything.
5. **test-policy-by-maturity** — When to write tests and how much, calibrated to
   repo maturity; prevents both under- and over-engineering across a varied fleet.
6. **repo-bootstrap** — The standard kit every repo should converge on
   (SessionStart hook, CLAUDE.md, .gitignore, minimal CI, settings.json
   permissions), triggered when a repo is missing pieces.

## Tier 2 — strong candidates

7. **claude-md-maintenance** — When a discovered repo fact earns a CLAUDE.md entry
   (and what belongs in skills instead), so per-repo context accretes instead of
   being re-learned every session.
8. **debugging-method** — Reproduce-first, hypothesis-loop discipline; no shotgun
   fixes, no "fixed" without a failing-then-passing repro.
9. **ci-triage** — Procedure for red CI on a PR: read the log before re-running,
   flaky-vs-real heuristics, when to fix vs rebase vs escalate.
10. **scope-control** — When a task balloons mid-flight, stop, re-scope, and split
    follow-ups into issues rather than growing a mega-PR.
11. **destructive-git-guardrails** — Hard rules around force-push, reset --hard,
    branch deletion, and history rewrites; cheap insurance everywhere.
12. **secrets-hygiene** — Never-commit rules for tokens/.env plus the exact
    remediation sequence if a secret lands in history (rotate first, then decide
    on rewrite).
13. **merge-conflict-resolution** — Resolve by re-applying intent from both sides
    rather than picking hunks, with a verify step after.

## Tier 3 — worth considering, lower leverage

14. **session-handoff** — Convention for ending a session mid-task (state dump in
    the PR description or a HANDOFF note); overlaps partially with #2.
15. **dependency-updates** — How to evaluate and apply version bumps; recurring
    chore, lower stakes.
16. **docs-discipline** — Update README/docs in the same PR as the behavior change
    they describe; may be better as one CLAUDE.md line than a skill.
17. **release-and-changelog** — Tagging/versioning/changelog conventions; only
    pays off if releases are actually cut across repos.
18. **branch-naming** — Too thin to be its own skill; fold into #2 or #4.

## Considered and cut

- **Progress-reporting style / clarify-vs-assume** — conversational behavior the
  harness already governs; better as global CLAUDE.md preferences than
  trigger-based skills.
- **Anything code-review shaped** — built-in `/code-review`, `/verify`, and
  `/security-review` already cover it; a library skill would fight them.
- **Language/framework-specific skills** — excluded by the cross-repo constraint.

## Authoring notes

Build chosen skills in the `model-routing` style: frontmatter `description` states
trigger *and* non-trigger conditions; body is short, opinionated defaults; add
local-vs-web surface caveats where behavior differs (#2, #9, #14 especially). If
skill-authoring (#1) is picked, build it first and use it to write the rest.
