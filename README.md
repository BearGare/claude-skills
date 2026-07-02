# claude-skills

Personal collection of Claude Code skills shared across repos.

## Layout

Each skill lives in `skills/<skill-name>/SKILL.md` (same format Claude Code
uses locally: YAML frontmatter with `name` and `description`, then Markdown
body).

## How this gets consumed

Projects that want these skills add a `SessionStart` hook
(`.claude/hooks/session-start.sh`, registered in `.claude/settings.json`)
that clones/pulls this repo and copies `skills/*` into that project's
`.claude/skills/` at the start of every Claude Code session — including on
Claude Code web, where each session starts from a fresh container.

This repo is the source of truth. Edit skills here; consuming repos pick up
changes automatically on their next session. Don't hand-edit the synced
copies inside `.claude/skills/` in a consuming repo — they'll be overwritten
on the next sync.

## Adding this to a new repo

Copy `.claude/hooks/session-start.sh` and the `SessionStart` entry in
`.claude/settings.json` from an existing consumer repo (e.g.
`BearGare/Harness-Learning-Hub`) into the new repo, and commit both.
