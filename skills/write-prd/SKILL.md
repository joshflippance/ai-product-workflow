---
name: write-prd
description: Write a one-page PRD grounded in the workspace's own research files and calibrated to a named audience. Use when the user asks to write, draft or upgrade a PRD, or invokes /write-prd.
---

# Write PRD

Project-scoped skill. Edit the file paths below to match your workspace before using it.

## Structure (fixed)

Every PRD produced by this skill uses exactly these sections, in this order:

- Problem Statement
- User (who, and the job to be done)
- Goals
- Non-Goals
- Success Metrics
- User Stories (3 to 5)
- Open Questions

One page. Plain declarative language. No opinions. Every point grounded in a workspace file and cited inline, for example `(strategy.md)` or `(research/interview-synthesis.md)`.

## Steps

1. **Identify the feature and the audience.** If the request does not say, ask which feature this PRD is for and who will read it (engineering, design, leadership, a named stakeholder).

2. **Read the relevant stakeholder profile** if one exists. This determines *calibration*, not content: what level of edge-case specificity or evidence framing to emphasise. Never facts to invent.

3. **Read the workspace broadly for grounding.** Strategy and project files, research and interview synthesis, prototype feedback, prior decision and spec-review documents, data files. Do not invent facts not found in these. If something is genuinely undecided, such as a success-metric target, say so rather than filling the gap.

4. **Draft each section:**
   - *Problem Statement* — cite the evidence directly, not a paraphrased opinion
   - *User* — cite the job to be done and the target persona or scenario from the research
   - *Goals and Non-Goals* — cite locked engineering and design decisions for what is in and what is explicitly deferred, and why it was deferred
   - *Success Metrics* — cite actual baseline numbers, and explicitly note where a target has not been set rather than inventing one
   - *User Stories* — 3 to 5, each grounded in a specific real quote or documented finding, never a generic story
   - *Open Questions* — pull real unresolved items already flagged elsewhere rather than inventing new ones

5. **Calibrate language to the audience.** More acceptance-criteria and edge-case precision for engineering. More user evidence and empty-state framing for design. More business-outcome framing for leadership. This changes emphasis and how much detail survives, never what is being asked for.

6. **Save** to a predictable path such as `docs/prd-<feature-slug>.md`. State the file path when done.

7. **Prompt to log** the PRD in the decision log and commit. Do not do it silently.

## The rule that matters

A model asked to produce a complete PRD will produce a complete PRD. The gaps arrive as confident sentences. Step 3's instruction to say "undecided" rather than fill the gap is the whole point of this skill.
