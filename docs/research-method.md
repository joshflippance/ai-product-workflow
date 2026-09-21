# Does this already exist, and is it worth building

A ten-step method for the research pass that happens before anyone writes a spec. Developed on a real product where the answer turned out to be "yes it is worth building, and for a different reason than I started with."

## The sequence

**1. Scope the brief before searching.** Settle four things first: is this a business, a side project, a learning exercise, or a portfolio piece? Which geography? How deep on competitors? What are the deliverables?

These answers change the research materially. "Side project plus portfolio" means skipping market-sizing theatre and going hard on jobs to be done, the graveyard, and pricing mechanics. Start searching before you have settled this and you will produce a lot of correct, useless material.

**2. Name the load-bearing primitive.** Before any competitive research, reduce the idea to the one mechanic everything else depends on. Not the feature list. The thing that, if you got it wrong, would make the rest pointless.

This is the step most people skip and the one that makes the research tractable. With the primitive named you stop asking "who else makes a product in this category," which returns dozens of unhelpful answers, and start asking "who else has solved this specific mechanic," which returns a handful, often in unrelated industries.

**3. Fan out on independent questions.** Identify the questions that do not depend on each other and research them in parallel, each with the same standing instruction: verify every figure at the source, mark anything unverified, no filler.

Parallel beats sequential whenever the questions are genuinely independent. The discipline is in noticing when they are not.

**4. Ask every competitor the same binary question.** Not "what features does it have." One or two yes/no questions, applied uniformly across every product you look at.

A uniform binary question across thirty products produces a defensible finding. A feature comparison produces a spreadsheet nobody reads and no conclusion you can defend in a room.

**5. Find the primitive solved in another industry.** If nobody in your category has solved your primitive, ask who else has the same shape of problem. The best design references usually come from outside.

The question to ask is structural: "who else has one person broadcasting to many people who must not see each other?" Answer that and you have found your references.

**6. Study the graveyard before the leaders.** Shutdown notices are public and unusually honest. Dead companies in your category will tell you what killed them in plain language, which is more than living competitors will do.

On the project this came from, the graveyard analysis produced more usable insight than the entire competitor feature list, and surfaced the two critical risks a feature comparison would never have found.

**7. Separate verified from unverified, in writing.** In the document, not in your head. Every figure carries where it came from and how confident you are. Vendor pages that block crawlers, figures taken from a competitor's comparison page, and anything you could not confirm all get marked as such.

This is also how you stay honest about the finding that would most weaken your own conclusion. Mark it clearly rather than letting it quietly disappear.

**8. Build the market bottom-up, or not at all.** If the only available market-size figures come from report mills publishing near-identical reports across shell brands, refuse them and say why.

"The category isn't tracked by anyone credible, so here is a bottom-up build" is a stronger answer than a number you cannot defend. Related: kill the familiar statistic that turns out to be an artifact. Repeating a well-known wrong number in front of anyone senior costs you the room.

**9. Write the kill criteria before the data arrives.** Decide what result would stop the project, in writing, while nobody is attached to the outcome.

Kill criteria written after the data are not kill criteria. They are a rationalisation with a threshold attached.

**10. Cut scope with the trade-off stated, not hidden.** When you defer something, write down why and the condition that would bring it back.

Cutting scope without explaining the trade-off is how a PM loses a stakeholder. Cutting it with the reasoning attached is how you get to make the next cut too.

---

## Judgement calls worth noticing

**Follow the data even when it contradicts the brief.** The obvious frame for the project this came from was one specific user situation. The data said the prevalence of that situation was declining while an adjacent one was rising. The better frame was the adjacent one, with the original as the acute segment. The brief was a hypothesis, not an instruction.

**The requirement behind the request is usually right; the words are usually wrong.** A stakeholder asked for something "really safe, like encrypted." Taken literally that is an architecture decision. Taken properly it was a requirement about what the product promises in public, and the enforceable risk lived in the marketing copy rather than the cryptography. Separating the requirement from the words is most of the job.

**Refusing a number is a finding.** Writing "we do not have a credible figure for this, and here is why" is a legitimate research output. It is also the one most likely to get you asked for the number again, which is why the reasoning has to be in the document.

## What was cheap and what was expensive

| Cheap | Expensive |
|---|---|
| Finding what exists, parallelised | Verifying prices at source. Vendors block crawlers and comparison pages are unreliable |
| The graveyard analysis. Shutdown notices are public and honest | Confirming a negative. You cannot prove absence, only check exhaustively and flag the gap |
| Pricing benchmarks from public filings and pricing pages | Regulatory detail, which moves faster than anything else in the research |

## The template

1. Scope the brief: intent, geography, depth, deliverable
2. Reduce the idea to its load-bearing primitive
3. Fan out parallel research on independent questions
4. Ask every competitor the same binary question
5. Find the primitive solved in another industry
6. Study the graveyard before the leaders
7. Separate verified from unverified, in writing
8. Build the market bottom-up or not at all
9. Write the kill criteria before the data arrives
10. Cut scope with the trade-off stated, not hidden
