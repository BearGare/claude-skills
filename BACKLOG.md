# Skill backlog

Remaining candidates from the 2026-07-02 library survey. Tiers 1 and 2 from that
survey are built and live in `skills/`. Every candidate must generalize across the
whole way of working — solo, natural-language prompting, multi-repo (varying
maturity), git/GitHub branch-and-PR, local Claude Code and Claude Code web
(ephemeral containers) — and nothing codebase- or domain-specific belongs here.

## Tier 3 — worth considering, lower leverage

1. **session-handoff** — Convention for ending a session mid-task (state dump in
   the PR description or a HANDOFF note); overlaps partially with
   ephemeral-session-hygiene.
2. **dependency-updates** — How to evaluate and apply version bumps; recurring
   chore, lower stakes.
3. **docs-discipline** — Update README/docs in the same PR as the behavior change
   they describe; may be better as one CLAUDE.md line than a skill.
4. **release-and-changelog** — Tagging/versioning/changelog conventions; only
   pays off if releases are actually cut across repos.
5. **branch-naming** — Too thin to be its own skill; fold into
   ephemeral-session-hygiene or pr-authoring.

## Considered and cut

- **Progress-reporting style / clarify-vs-assume** — conversational behavior the
  harness already governs; better as global CLAUDE.md preferences than
  trigger-based skills.
- **Anything code-review shaped** — built-in `/code-review`, `/verify`, and
  `/security-review` already cover it; a library skill would fight them.
- **Language/framework-specific skills** — excluded by the cross-repo constraint.

## Authoring notes

Build new skills per `skills/skill-authoring/SKILL.md`.
