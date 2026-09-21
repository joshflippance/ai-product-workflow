# How I run product work with AI

The reusable parts of my product process: the research method, the working rules, and the Claude Code skills I actually use. Everything here came out of real projects and has been generalised so it drops into yours.

I am a product leader, not an engineer. What I direct AI to do is product work: research a category, draft a spec, argue against my own architecture, review a design for the failure I have not thought of. The interesting question is not whether a model can write a PRD. It is what you have to put around it so the output is worth acting on.

Three things do most of that work, and all three are in this repo.

**Ground every claim in a named file.** Nothing in a document I ship is there because the model produced it fluently. Every assertion cites the file it came from, and "this is genuinely undecided" is a valid output. A model asked for a complete document will produce a complete document, and the gaps arrive as confident sentences.

**Separate verified from unverified in writing.** Not in my head, in the document. A research file that does not mark its weak sources is a file that will be quoted back at you in six months.

**Decide the kill criteria before the data arrives.** Written while nobody is attached to the outcome. This is the single cheapest discipline here and the one most often skipped.

---

## What's here

| | |
|---|---|
| [docs/research-method.md](docs/research-method.md) | A ten-step method for "does this already exist and is it worth building." The most load-bearing thing in this repo. |
| [docs/hard-rules.md](docs/hard-rules.md) | The prohibitions I put in every project's CLAUDE.md, and why each one exists. Includes the agent identity rule and the documentation-as-done rule. |
| [skills/](skills/) | Three working Claude Code skills: write a grounded PRD, save a session cleanly, draft a weekly status. |
| [reference/ai-feature-guardrails.md](reference/ai-feature-guardrails.md) | Six gates for scoping an AI feature. Synthesised from a named article, not my own framework. Cited inside. |

---

## The research method, in one paragraph

Scope the brief before searching. Reduce the idea to its load-bearing primitive, then research that rather than the category. Fan out parallel searches on independent questions. Ask every competitor the same binary question rather than building a feature matrix. Find the primitive solved in a different industry. Study the graveyard before the leaders. Separate verified from unverified in writing. Build the market bottom-up or not at all. Write the kill criteria before the data arrives. Cut scope with the trade-off stated rather than hidden.

The full version, with what each step actually buys you and what it costs, is in [docs/research-method.md](docs/research-method.md).

## The skills

Three skills, each solving a different failure mode.

**write-prd** solves ungrounded documents. Fixed seven-section structure, every claim cited inline to a file, and an explicit instruction to say "undecided" rather than invent a target. Audience calibration changes emphasis and detail, never facts.

**session-save** solves context rot. At the end of a session it sorts what was learned by destination, proposes a diff file by file, and waits for approval. It ends with the rule that matters most: if nothing warrants an update, say so rather than inventing changes to justify the save.

**weekly-status** solves the status update that reports discussion as progress. It reads the decision log rather than the conversation, so "what actually got decided this week" is the input.

All three are project-scoped by design. Copy them into `.claude/skills/` and edit the file paths to match your workspace.

## What this repo does not have yet

Honest list, because the gaps are as informative as the contents:

- **Blank document templates.** I have strong filled-in instances of a PRD, a decision log, an evidence file and a competitive matrix. I do not yet have them as templates, and generalising from a single instance produces something closer to invention than documentation.
- **Eval sets.** The guardrails doc says build evals. I have built them inside individual projects and none of them are reusable enough to publish.
- **Worked before-and-after examples.** Nothing here shows the prompt, what came back, and what I changed. That is the most useful thing I could add and it is the next thing I intend to add.

---

## Seeing it applied

Two case studies that use this method end to end:

- [circle-case-study](https://github.com/joshflippance/circle-case-study) — designing a product around a single hard constraint, and the security review that followed
- [mapping-copilot-case-study](https://github.com/joshflippance/mapping-copilot-case-study) — measuring an AI system so its mistakes are visible rather than merely rare

Josh Flippance · [joshflippance.com](https://joshflippance.com) · [LinkedIn](https://linkedin.com/in/joshflippance)
