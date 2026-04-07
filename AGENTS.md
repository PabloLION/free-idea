# Agent Instructions

This is an idea repository — no code, just idea tracking via GitHub issues and
local markdown files. Use **bd** (beads) for task tracking.

## Project Context

Ideas are tracked in two places:

- **GitHub issues** — published ideas with research, examples, and analysis
- **`.dev/issues/`** — local drafts and research threads

## GitHub Actions Require Confirmation

Never create, close, edit, or comment on GitHub issues without explicit user
confirmation first. You may batch multiple actions into one confirmation, but
the user must verbally approve before any GitHub write operation executes.

This applies to: `gh issue create`, `gh issue close`, `gh issue edit`,
`gh issue comment`, `gh pr create`, and any other GitHub-facing write.

## Working on Ideas

When the user describes a new idea:

1. Research whether similar projects/proposals exist
2. Draft the idea as a local issue file in `.dev/issues/`
3. Let the user review before publishing to GitHub
4. After posting, delete the local draft

When researching, use `searchnet:broad-search` for discovery questions and cite
sources in the GitHub issue.

## Local Issue Threads

Local issue threads are markdown files for tracking ideas and research that
aren't published on GitHub.

### Naming Pattern

```text
issue-{number}.{kebab-case-title}.md
```

Examples:
- `issue-53.zellij-layout-sharing-platform.md`
- `issue-51.vim-learning-game.md`

### Location

Store in `.dev/issues/` directory.
