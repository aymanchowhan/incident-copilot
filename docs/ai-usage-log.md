# AI Usage Log

A record of meaningful tasks done with AI assistance. Add a new entry at the
top of the "Entries" section after each task.

## Entry template

```markdown
### YYYY-MM-DD — <short task title>

- **Phase:** <1–10>
- **Tool / model:** <e.g. Claude Code (Opus 5.5)>
- **Task:** <what was asked>
- **What the AI did:** <files created/changed, commands run>
- **Human review / changes:** <what you checked, corrected, or rejected>
- **Outcome:** <result; follow-ups or open questions>
```

## Entries

### 2026-10-04 — Project scaffolding docs

- **Phase:** 1
- **Tool / model:** Claude Code (Opus 5.5)
- **Task:** Create CLAUDE.md, this log, and README.md; verify .gitignore and
  that no secrets are tracked.
- **What the AI did:** Created `CLAUDE.md` (goal, stack, layout, working rules),
  `docs/ai-usage-log.md`, `README.md`. Confirmed `.gitignore` already covers
  `.env`, `.venv/`, `__pycache__/`. Ran `git ls-files` — only `.gitignore` and
  `docs/decision-log.md` were tracked; no secrets.
- **Human review / changes:** <fill in>
- **Outcome:** Repo has baseline docs and working rules for phase 1.
