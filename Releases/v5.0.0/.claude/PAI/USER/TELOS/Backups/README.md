# Backups

> 🎯 SAMPLE TEMPLATE — This directory ships empty. PAI tools that bulk-edit your TELOS files (interview phases, migrations, generators, refactors) write a timestamped snapshot of the affected files here BEFORE making changes, so you can always roll back.

## Purpose

TELOS data is the most personal layer of PAI. A bad regex or a botched migration shouldn't be able to destroy years of accumulated reflection. Anything that programmatically edits files in `../` writes a backup here first.

## File naming convention

```
{ORIGINAL_FILENAME}.{YYYYMMDD-HHMMSS}.bak.md
```

Example: `GOALS.20260429-153012.bak.md` was a copy of `GOALS.md` taken before an edit on 2026-04-29 at 15:30:12.

## Retention

PAI does not auto-delete backups. They're cheap to keep and expensive to lose. Clean this directory by hand if it ever grows unwieldy.

## Restoring

To roll back a file, copy the desired backup over the live file:

```bash
cp ~/.claude/PAI/USER/TELOS/Backups/GOALS.20260429-153012.bak.md \
   ~/.claude/PAI/USER/TELOS/GOALS.md
```

Then regenerate the summary:

```bash
bun ~/.claude/PAI/TOOLS/GenerateTelosSummary.ts
```

## Privacy

Same as the rest of `TELOS/` — never leaves your machine, stripped from public PAI releases.
