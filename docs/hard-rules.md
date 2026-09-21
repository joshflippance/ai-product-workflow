# Hard rules

The prohibitions I put in a project's `CLAUDE.md` before an agent touches anything. Three separate projects converged on the same shape, which is why I now treat it as a standard rather than a one-off.

The shape: a short list of things the agent may never do, each with the reason attached. Not guidance, not preferences. Prohibitions with rationale, because an agent that understands why a rule exists handles the case the rule did not anticipate.

---

## Data and credentials

**No real user data in any prompt, file, screenshot or log.** Synthetic or redacted, always. This is the rule most likely to be broken by accident, usually by pasting a real record into a prompt to debug something.

**No production credential in any agent session, connector or tool.** Production secrets live in the deployment environment and nowhere else. If the agent needs a credential to do the task, the task is wrong.

**Every new dependency verified against the registry before install.** Agents suggest packages confidently, including ones that do not exist or that typosquat ones that do. This is a supply-chain rule, and it is cheap.

## Agent identity and review

**The agent pushes branches and opens pull requests under an identity that cannot approve or merge.** With one human, an author cannot approve their own pull request, so review only means something if the agent is not you.

This one is easy to dismiss on a solo project and it is the one I would keep. It is what makes the review step real rather than ceremonial.

## Tests

**Tests that encode the product's core guarantee may never be skipped, marked as only, or left as todo.** Name them explicitly in the rules so there is no ambiguity about which ones those are. Every project has tests it can afford to skip temporarily. The rules exist to name the ones it cannot.

**Structural boundaries are enforced by tooling, not convention.** Import rules, layer boundaries and access patterns that are merely documented will drift. Lint them.

## Documentation as definition of done

The rule that solves the failure mode every AI-assisted repo has: documentation that quietly stops being true.

Map change types to the document each one obligates you to update, put the table in the rules, and apply one test before every commit:

> Does this change make any sentence in the documentation above untrue?

If yes, the change is not done. This works because it is answerable. "Keep the docs up to date" is not.

## Copy and tone

Worth stating explicitly, because an agent left alone will produce cheerful generic product copy:

> Plain and human. No jargon, no exclamation marks. Errors say what happened and what to do next.

---

## Why prohibitions rather than instructions

An instruction tells an agent what to do in a case you anticipated. A prohibition with its reason attached tells it what matters, which generalises to the case you did not.

"Never put a production credential in an agent session" covers the situation you wrote it for. "Because an agent session is not a trusted environment and its transcript may be stored" covers the twenty you did not.
