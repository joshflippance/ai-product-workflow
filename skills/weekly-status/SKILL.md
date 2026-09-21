---
name: weekly-status
description: Generate a weekly status update grounded in the current phase and recent decision-log entries rather than in what was discussed. Use when the user asks for a weekly or status update, or invokes /weekly-status.
---

# Weekly Status

Project-scoped skill. Edit the file paths below to match your workspace before using it.

## Steps

1. **Ask who this is for**, and whether the user has raw notes from the week to fold in. If they do not have notes ready, offer to draft entirely from the workspace files.

2. **Read for grounding:**
   - the project file, for the current phase
   - the last five to seven decision-log entries, for **what actually got decided this week, not what was discussed**
   - the strategy file's open questions, for anything unresolved worth flagging

3. **Calibrate to the audience.** If a stakeholder profile exists, use it to set tone and length. It never invents content. No profile is fine: say so and draft in a neutral, direct tone.

4. **Draft a short update in four parts:**
   - *This week* — what actually happened, grounded in decision-log entries and any notes provided. Real decisions, not discussion.
   - *Status* — current phase, one line
   - *Next* — what is happening next, and by when if a date exists in the workspace
   - *Blockers and asks* — anything genuinely open that needs someone else's input

5. **Show the draft and ask before finalising.** Do not save silently.

6. **On approval**, offer to save it to a dated path and log the update itself in the decision log.

If the user's notes contradict the decision log, ask rather than silently picking one.

## The rule that matters

Step 2. Reading the conversation produces a status update full of activity. Reading the decision log produces one full of decisions. The second is shorter and is the only one worth sending.
