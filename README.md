# Support, evidence first

I am a support professional who builds prototypes to test my assumptions about AI in support, keeps the negative results, and marks where the evidence stops.
This page groups that work by the support question each project answers.
The thesis is simple: evidence before action.

## When should AI act, and when should a person?

### Voice Support

- **Problem:** An AI can misread a customer and sound certain before support has enough evidence to act safely.
- **What I built or tested:** A controlled typed-and-voice prototype where AI proposes what the customer means and fixed rules choose the allowed support response.
- **What happened:** The prototype can provide visual guidance, ask bounded troubleshooting questions, or prepare a mock human handoff; it has not been tested with customers.
- **What I decided:** The AI can raise the risk of a case but never lower it. Rules decide what support may do; the AI only proposes what the customer meant.
- **Where to look:** [Voice Support case study](https://github.com/gititya/voice-support-case-study)

## How do I know a handoff is good enough?

### Handoff Gate

- **Problem:** A polite, confident handoff can still omit the account, charge, claim, evidence, or open questions the next person needs.
- **What I built or tested:** A rule-based gate for AI-to-human billing handoffs and support-to-engineering issue reports.
- **What happened:** In synthetic cases, complete notes moved forward and notes with required facts missing stayed held with a specific reason; the B2B grounding check remains a disclosed word-overlap stopgap.
- **What I decided:** A handoff that is polite, confident, and missing the account, the charge, or the claim is not a handoff. The gate holds it and says exactly what is missing.
- **Where to look:** [Handoff Gate](https://github.com/gititya/handoff-gate)

## How do I know the support was actually good?

Quality Agency grades one reply. Support Evals grades the whole journey. They remain separate because those are different support questions.

### Quality Agency

- **Problem:** A polished answer can ignore policy, invent authority, misdiagnose the issue, or leave the next person with a poor handoff.
- **What I built or tested:** Five small-model reviewers for source use, process, unsupported promises, diagnosis, and handoff completeness, tested on labeled fixtures.
- **What happened:** The vague rubric caught more bad source-of-truth replies than the detailed versions, but even the best setup produced false-safe decisions that still require human review.
- **What I decided:** For a small local model, the vague rubric beat the detailed one. And the number that matters is how many bad replies the judge waves through, not how many good ones it passes.
- **Where to look:** [Quality Agency](https://github.com/gititya/support-quality-agency)

### Support Evals

- **Problem:** Grading one reply misses failures that happen across investigation, action, outcome, closure, and handoff.
- **What I built or tested:** A journey-level QA framework using fictional cases, saved traces, controlled product states, and local reference implementations.
- **What happened:** It catches failures represented in those cases, including steps taken before supporting facts arrived; it has not been connected to a real support product.
- **What I decided:** A reply is evidence of communication, not of resolution. A journey fails if a troubleshooting step used a fact that had not arrived yet.
- **Where to look:** [Support Evals](https://github.com/gititya/support-evals)

## What does support data tell product, and how many people do I still need?

### Signal

- **Problem:** Free-form complaint themes can sound useful while hiding why each complaint belongs and what the result does not prove.
- **What I built or tested:** A tool that places public TransUnion credit-report disputes into a fixed evidence taxonomy before writing a product brief.
- **What happened:** Free-form clustering failed through token limits, non-converging merges, and scrambled complaint references; the fixed buckets produced a checkable saved brief for one domain.
- **What I decided:** Free-form clustering of complaints failed three ways before I gave the model a fixed set of buckets and made it write only inside them. The brief carries a “what this is not” section on purpose.
- **Where to look:** [Signal](https://github.com/gititya/support-signal)

### Capacity Planning

- **Problem:** Cutting headcount by the same percentage as automated contacts ignores the slower work left for people.
- **What I built or tested:** A three-stage what-if model for contacts attempted by AI, contacts resolved by AI, and the harder work returned to people.
- **What happened:** Its scenarios show a staffing floor and show how the naive average can understate the people needed; it is a pressure test, not a forecast or staffing recommendation.
- **What I decided:** AI takes the easy contacts first, so what is left is slower. There is a floor you cannot staff below, and the naive average under-hires by dozens of people.
- **Where to look:** [Capacity Planning](https://github.com/gititya/support-capacity-planning)

## What did I test and kill?

### Early prediction experiment

- **Problem:** A speculative copilot would only help if the opening of a support call revealed the specific cause early enough to act.
- **What I built or tested:** A blind test that showed a predictor only the first six turns of synthetic support calls and hid the answer key.
- **What happened:** Specific-cause accuracy was 14% on 51 calls and 2% on 48 harder calls, against a 60% bar; full transcripts reached 92% on the 48 harder calls.
- **What I decided:** Support calls do not reveal the specific cause early. I killed the speculative copilot idea.
- **Where to look:** [Early prediction experiment](https://github.com/gititya/support-early-prediction-experiment)

### Intent classifier experiment

- **Problem:** Strong synthetic validation scores did not show whether an intent classifier understood natural customer language.
- **What I built or tested:** Three model families trained or fitted on the same synthetic source and checked on the same ten natural messages.
- **What happened:** The models landed between 40% and 60% on natural language (n=10), where one changed answer moves the result by ten points.
- **What I decided:** Three model families, same 40–60% on natural language (n=10). The ceiling was the synthetic training data, not the model.
- **Where to look:** [Intent classifier experiment](https://github.com/gititya/support-intent-classifier-experiment)

### Copilot Lab

- **Problem:** A support AI can reach the right cause for the wrong reason by stating it before the evidence exists.
- **What I built or tested:** A fixture-driven investigation replay that keeps facts, unknowns, possible causes, ruled-out causes, and the next check separate as evidence arrives.
- **What happened:** The predictive mock reached the correct final causes but made 29 premature final-cause claims across 12 fixture cases; no support representative has used the simulator.
- **What I decided:** I stopped scoring whether the AI guessed the cause and started scoring whether it said the cause before the evidence existed. A right answer said too early is a failure.
- **Where to look:** [Copilot Lab](https://github.com/gititya/support-copilot-lab)

## Also built, private

- **Internal Desk:** reads local ticket, order, and charge records for representative work; it is not connected to Voice Support.
- **Support Binder:** pins exact versions and replays proofs so drift stays visible.
- **Support State Core:** keeps fixed support decisions separate from AI interpretation.
- **Screen-Aware Support:** points to an approved control without clicking it.
- **Transcript Processing:** blocks a rewrite when the meaning may have changed.
- **Muesli Integration:** tested registered guidance capabilities against one pinned third-party app build without taking action in the app.
- **Support Call Generator:** creates synthetic calls with hidden answer keys for blind tests.
- **Fake B2C App:** supplies a controlled customer setting for repeatable support tests.

## Evidence boundaries

- Most results use synthetic scenarios, fictional cases, local fixtures, or saved traces.
- Owner-run checks show what happened on one machine and one recorded setup; they do not show broad reliability.
- No project here has been validated with customers or production customer data.
- No result proves customer impact, production reliability, or broad model quality.
- Passing checks prove only that the recorded behavior still matches the stated rules; small samples, misses, rejected ideas, and known limits remain visible.
