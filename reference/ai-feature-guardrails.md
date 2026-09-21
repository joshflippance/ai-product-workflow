# AI Feature Guardrails

> **Provenance.** This is not my framework. It is a structured synthesis of one article, kept in this shape because I load it into project knowledge before scoping an AI feature and it is more useful as gates than as prose. Source and figures are cited below. The "Instructions for AI build agents" section at the end is mine.

Reusable context for any product build that includes an AI feature. Load this file into the project (Claude project knowledge, Lovable project knowledge, CLAUDE.md, or a spec folder) before scoping, building, or shipping AI functionality.

Source: "7 Mistakes Companies Make When Building AI Features," Iria Fredrick Victor (Fredsazy), May 4, 2026. Figures below are as cited in the article. The article does not name its underlying studies, so treat them as directional.

---

## The short version

1. Start from a painful user problem. AI is one possible answer, not the starting point.
2. The demo is the easy 80%. Plan the last 20% (evals, fallbacks, hardening) from day one.
3. Check the data before committing to the feature.
4. Define what good output looks like before building. Test against it on every change.
5. Shipping is where the work starts. Monitor output quality, not only uptime.
6. Cost the whole thing at production scale, not just API calls in dev.
7. One narrow pilot at a time. Ship it or kill it before starting the next.

---

## Why this matters

The article cites these figures:

- 80% of AI projects fail, about double the rate of traditional IT projects
- 42% of companies abandoned most AI initiatives, up from 17% two years prior
- The average organisation scrapped 46% of AI proofs of concept before production
- One team built 80% of a system in a week. The last 20% took eight months and tripled the budget.

The failures are mostly product and delivery discipline. The models are rarely the problem.

---

## Gate 1: Problem

**Rule:** No AI feature without a named user problem that is painful enough to change behaviour.

Answer before building:

- What specific user problem does this solve?
- How often does it happen, and how painful is it today?
- Would a rule-based solution, a better non-AI flow, or doing nothing solve it well enough?
- Is the gain a step change (large time saved, task eliminated, new capability) or marginal?

**Fails the gate if** the main reason is "it's faster" or "it feels modern."

---

## Gate 2: Data

**Rule:** Audit the data the feature depends on before committing to it.

Answer before building:

- Is the data available and accessible to the feature?
- Is it consistent, complete, and clean enough to query or train on?
- Are there duplicates, missing fields, or silos the current product quietly works around?
- Who owns data quality going forward?

**Fails the gate if** any answer is no. Fix the data first.

The article notes that teams who succeed put 50% to 70% of AI budget into data infrastructure, quality, and governance.

---

## Gate 3: Definition of good (evals)

**Rule:** Write down what correct output looks like, and build the eval set before the feature ships.

Build:

- A representative input set, including edge cases, ambiguous inputs, and adversarial prompts
- Clear pass or fail criteria per input, or a scoring rubric
- An automated eval run that triggers on prompt changes and model updates

Test specifically for:

- **Hallucination:** confident, wrong answers that normal functional tests miss
- **Edge cases:** real inputs are messier than test data
- **Model regression:** vendor model updates change behaviour quietly
- **Prompt injection:** users crafting inputs to manipulate the system
- **Scale:** results on 100 samples don't predict results on 10,000 real inputs

**Fails the gate if** "good" is judged by eyeballing a few outputs.

---

## Gate 4: Production readiness

**Rule:** Build production pieces alongside the feature, not after launch.

Required before launch:

- **Fallback behaviour** for errors, timeouts, and low confidence output
- **Output quality monitoring**, separate from system health
- **User feedback signals:** thumbs up or down, corrections, abandonment
- **Feedback loop** that routes those signals back into the eval set
- **Drift alerts** on output characteristics
- **Manual review cadence** on a sample of real outputs

**Fails the gate if** monitoring is uptime and error rates only.

---

## Gate 5: Cost

**Rule:** Model the full cost at projected production volume before committing.

Include:

- Prompt engineering and iteration time
- Eval infrastructure
- Monitoring and observability
- Edge case discovery and handling
- Ongoing maintenance when models change
- Token and compute cost at real usage volume
- Contingency for unknown edge case work

Calibrate with a small pilot before scaling.

**Fails the gate if** the estimate covers API calls in development only.

---

## Gate 6: Pilot, then scale

**Rule:** One narrow, high pain use case with a measurable outcome. Ship it, measure it, then decide.

- Set a baseline before launch
- Measure the user outcome (time saved, error rate, decision quality), not adoption
- No new AI pilot until the current one has shipped to production or been explicitly killed
- If it works, repeat the pattern. If it doesn't, capture the learning and move on.

**Fails the gate if** several AI initiatives run in parallel with no shipped result.

---

## AI feature brief (fill in before build)

```
Feature name:
User problem (one sentence):
Who has it, how often:
Current workaround:
Why AI (and why not rules or a better flow):

Data sources:
Data readiness status (available / consistent / complete / clean):
Data gaps to fix first:

Definition of good output:
Eval set location and size:
Top edge cases:
Injection or misuse risks:

Fallback when AI fails or is low confidence:
Quality metrics monitored:
User feedback signals captured:
Review cadence:

Success metric (user outcome):
Baseline:
Target:
Kill criteria:

Cost estimate at production volume:
Pilot scope and duration:
Decision date (scale or kill):
```

---

## Pre-ship checklist

- [ ] Named user problem, validated with real users
- [ ] Simpler non-AI options considered and ruled out
- [ ] Data audited and gaps fixed
- [ ] Definition of good output written down
- [ ] Eval set built, including edge cases and adversarial inputs
- [ ] Automated eval run on prompt or model changes
- [ ] Fallback behaviour designed and tested
- [ ] Output quality monitoring live
- [ ] User feedback signals captured and routed to evals
- [ ] Full cost modelled at production volume
- [ ] Success metric and baseline set
- [ ] Kill criteria and decision date agreed

---

## Post-launch cadence

- **Weekly:** review a sample of real outputs, triage feedback, add failures to the eval set
- **On every model or prompt change:** full eval run before release
- **Monthly:** compare user outcome metric to baseline, check cost against estimate
- **At decision date:** scale, iterate, or kill. Write down why.

---

## Instructions for AI build agents

When helping build or spec an AI feature in this project:

1. If the brief has no named user problem, stop and ask for one before writing code.
2. Flag when a rule-based or non-AI approach would likely work as well.
3. Never ship a happy path only. Every AI call needs error, timeout, and low confidence handling in the UI.
4. Log prompts, inputs, outputs, model version, and latency for every AI call, with user data handled per the project's privacy rules.
5. Create or update an eval file (for example `/evals/<feature>.json`) alongside any prompt change.
6. Keep prompts in versioned files, not inline strings scattered through the code.
7. Add a user feedback control on AI output (thumbs up or down, or edit capture).
8. Estimate token usage per request and flag anything likely to be expensive at scale.
9. Treat all user input to prompts as untrusted. Guard against prompt injection.
10. Measure the user outcome defined in the brief. Don't treat clicks as success.

---

## Red flags

- "Competitors have it, so we need it"
- The demo looked great, so the plan is to ship next week
- "We'll sort the data out later"
- Testing means trying a few prompts by hand
- Monitoring is the same as any other endpoint
- Budget covers API calls and nothing else
- Four AI pilots running, none shipped
- Success is measured by how many users clicked the AI button
