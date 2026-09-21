---
name: session-save
description: End-of-session hygiene pass. Reviews what was discussed and decided, then proposes updates to the project's files, asking for approval before writing anything. Use when the user types /session-save or asks to wrap up or save session progress.
---

# Session Save

Project-scoped skill. Edit the file list below to match your workspace before using it.

## What each file is for

Define this once, per project, and the sorting step becomes mechanical:

- `CLAUDE.md` — orientation only: what the product is, who is involved, an index of the working files. Never duplicate content that lives in another file.
- `project.md` — what the product is, the team, the current phase, key stakeholders
- `strategy.md` — hypothesis, supporting evidence, proposed direction, goals, non-goals, success metrics, open questions
- `change_log.md` — audit trail of decisions. Format: `Date — Decision — Rationale — Decided by`, appended chronologically

## Steps

1. Review the session for anything that changes the project's understanding: new facts, a changed hypothesis, stakeholder or context updates, decisions made.

2. Sort findings by destination. Facts to the project file, hypothesis and direction to the strategy file, decisions to the change log. Anything that fits nowhere, ask before creating a new file.

3. Check the orientation file for hygiene. Do not duplicate content that now lives elsewhere. Only update it if the product description, the people, or the file index actually changed.

4. Present a proposed diff, file by file, before writing anything. Wait for approval.

5. On approval, write the changes, matching each file's existing structure and tone.

6. **If nothing warrants an update, say so. Do not invent changes to justify the save.**

## The rule that matters

Step 6. A model asked to summarise a session will always find something to write down, and a project file that accumulates restated conversation becomes useless faster than one that is out of date. The empty result is a valid result.
