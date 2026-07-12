# PROJECTS — Your Project Registry

`PROJECTS.md` is the table of every project you work on, plus the natural-
language aliases the DA uses to route requests like "deploy the blog" or
"check the work hub" to the right repo. PAI loads this at every session
start via `CLAUDE.md` `@-import`.

## File

| File | What it holds |
|------|----------------|
| `PROJECTS.md` | Markdown table of projects + a routing-aliases table. Loaded at startup. |

## Why this matters

Without `PROJECTS.md`, the DA has no way to map "the blog" to a specific
repository — it would have to ask every time. With a populated table, you
can say "push the latest commit on the blog" and the DA already knows the
path, the deploy command, and the stack.

## Format

The table has five columns:

| Project | Path | URL | Deploy | Stack |
|---------|------|-----|--------|-------|
| **Blog** | `~/code/blog` | example.com | `bun run deploy` | Astro, TS |

Plus a routing-aliases section underneath:

```markdown
## Routing Aliases

When you say... | The DA routes to...
---|---
"my blog", "the blog", "site" | Blog
```

Add as many rows as you have projects. Keep entries short — the DA reads
the whole table at every session start, so noise costs context.

## How to populate

**Easiest:** run `/interview` after install — the projects phase asks
about your active projects one at a time and appends rows.

**By hand:** open `PROJECTS.md` and edit the table directly. The shipped
file has one example row; replace or extend it.

**Incrementally:** add a row whenever you start a new project. Cheaper
than reconstructing later.

## Privacy

Nothing in this directory ships in a public PAI release. The release
builder overlays a generic public-default scaffold; your real project
list stays on your machine.
