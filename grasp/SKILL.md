---
name: grasp
description: Build a big-picture mental model and learning priorities for an unfamiliar field, subject, or product. Use when the user wants to grasp the main ideas, relationships, development, and trade-offs before details. Not for narrow factual questions, step-by-step tool instructions, or an already-defined implementation task.
---

# Grasp — 抓住主脉

Help the user acquire a compact, transferable mental model of an unfamiliar domain before investing in details. Optimize for structural understanding and sound judgment, not exhaustive coverage.

## Frame the learning objective

Infer or establish:

- what the user wants to do with the knowledge;
- their current level;
- familiar concepts or experience that can serve as bridges;
- the available time or desired depth;
- whether the domain is stable or fast-moving.

Proceed with reasonable assumptions when these do not materially change the result. State important assumptions briefly.

Choose depth to match the user's learning budget. These are scope guides, not promises of mastery or instructions to keep running for that duration:

- **Quick orientation (about 5–15 minutes of user reading):** definition, a small map, a few governing ideas, one concrete example, and the highest-value next step.
- **Domain map (about 1–3 hours of user study):** add major approaches, their assumptions and boundaries, relevant development, representative evidence, and a prioritized reading/practice path.
- Longer learning plans, reading lists, and practice projects are optional extensions only when requested.

Default to quick orientation when depth is unspecified. Expand when the user asks for a review, comprehensive map, or deeper understanding. Treat short follow-ups as targeted updates to the existing map rather than repeating the whole workflow.

## Adapt the lens to the subject

Use the following as optional lenses; combine them when needed:

| Subject | Structural focus |
|---|---|
| Science or research | Questions, theories, evidence, competing explanations |
| Technical system | Components, mechanisms, dependencies, trade-offs, failures |
| Tool or product | User tasks, core objects, workflow, capabilities and limits |
| Practical skill | Subskills, prerequisites, feedback, representative practice |
| Humanities or thought | Central questions, concepts, schools, interpretive disagreements |
| Business or industry | Value chain, participants, incentives, economics, competition |

Do not force benchmarks, papers, a single original problem, or a linear progress story onto every subject. Use appropriate evidence such as demonstrations, worked examples, primary texts, or observed outcomes. Present a taxonomy as a useful provisional lens, not a uniquely correct partition.

## Build the map before descending

Begin at low resolution. Select the dimensions that explain this subject:

1. **Original problem** — why the field exists and how the problem was handled before it.
2. **Boundary** — what belongs to the field, what is adjacent, and what is outside scope.
3. **Invariants** — the objects, goals, constraints, operations, and success criteria that remain meaningful across competing approaches.
4. **Taxonomy** — mutually useful categories into which new information can be placed.
5. **Causal evolution** — the sequence `problem → solution → exposed failure → next solution`, not merely a chronology of names.
6. **Core trade-offs** — usually three to five tensions that explain why multiple approaches coexist.
7. **Evaluation** — how claims are tested, which metrics are proxies, and what a strong baseline is.

Prefer a compact table, tree, or flow when it materially clarifies the map.

Use one concrete example early and revisit it to explain key relationships. Define necessary terms on first use; avoid replacing detail overload with an equally dense list of abstract labels. Distinguish documented historical causes from a simplified teaching reconstruction, and show parallel branches where relevant.

## Decide when to use external information

Use existing knowledge to propose the stable conceptual skeleton, subject to higher-priority tool and verification requirements. Choose external checks by claim, not merely by topic:

- Stable, well-understood fundamentals can usually be explained directly when the user has not requested research or source verification.
- Browse when the user requests research, search, verification, or current information; when discussing changing capabilities, versions, prices, leading approaches, or recent evidence; when a specific unread source is supplied; or when a consequential claim is uncertain.
- Model release cadence does not establish its knowledge cutoff, factual completeness, or the freshness of any particular claim. Never infer that a new model eliminates the need for verification.
- When supplied materials answer the question, use them within their dated scope. For a current-state request, check whether relevant developments supersede them.
- If browsing is unavailable or the user forbids it, provide the stable map, identify which current claims remain unverified, and avoid claiming a current ranking or exhaustive survey. Do not fabricate citations.

When browsing, search to resolve explicit gaps in the map. Prefer original papers, official documentation, primary texts, and authoritative syntheses. Check publication/version dates and cite the specific claims supported. Separate stable foundations from recent developments and distinguish reported results, independent evidence, and your inference.

## Select evidence for information gain

Do not collect many near-duplicate sources. For research-oriented subjects, choose from these source roles as needed; filling all five is not a quota:

- one foundational work or origin;
- one strong survey or synthesis;
- one representative mainstream approach;
- one challenger, negative result, or failure analysis;
- one comparative benchmark or real-world evaluation.

Prefer primary and authoritative sources. For fast-moving topics, verify the current state rather than relying on memory. Distinguish author-reported results, independent evidence, consensus, and inference.

Read sources in passes:

1. **Locate:** problem, route, claim, and place in the map.
2. **Understand:** inputs, mechanism, outputs, assumptions, and failure modes.
3. **Judge:** baseline quality, metric validity, total cost, generalizability, and missing evidence.

Most sources need only the first pass. Reserve deeper passes for sources that change the map, resolve a contradiction, or directly serve the user's intended application.

Stop expanding the search once the core map and decision-relevant claims have adequate support and additional sources no longer change the structure or judgment. If a consequential contradiction remains, investigate it within scope or expose it as unresolved; repetition alone is not confirmation. Return a useful synthesis within the user's budget rather than extending research indefinitely.

## Manage resolution deliberately

Use four levels of knowledge:

- **L1 — Awareness:** know that the concept exists.
- **L2 — Position:** know what problem it solves and where it belongs.
- **L3 — Mechanism:** explain how and why it works, including assumptions.
- **L4 — Implementation:** reproduce, modify, or apply it reliably.

For initial orientation, aim for broad L2 coverage, L3 depth on the few structural ideas, and L4 only on material needed for the user's immediate goal. Adjust this allocation when the user requests implementation or deep expertise.

Maintain a mental or explicit detail parking lot. Defer a detail unless at least one condition holds:

- it can change the high-level conclusion;
- it distinguishes major competing approaches;
- it is a prerequisite for understanding the mechanism;
- it is required for the user's next decision or practice task;
- it exposes a serious limitation, cost, or risk.

Do not confuse unexplored details with unimportant details. Mark consequential uncertainties explicitly.

## Default deliverable

Deliver the guide directly in the conversation, followed by the optional adaptive understanding check. Generate a Markdown file when the user wants to save or share it; after the check, include demonstrated gaps and corrections if useful. Generate HTML only when requested or when diagrams and interaction materially improve understanding. Do not create files or a full literature review by default.

## Produce a reusable mental model

For quick orientation, prioritize the definition, map, governing ideas, concrete example, and next step. For a fuller map, select useful additions from:

- a plain-language one-sentence definition;
- a macro map or classification tree;
- the causal development path;
- three to five governing trade-offs;
- the leading approaches and their capability boundaries;
- what is established, disputed, and unknown;
- a prioritized learning path stating what to learn now, later, and only when needed.

When useful, include a transfer section connecting the new domain to familiar systems or disciplines. Label analogies as analogies and name where they break.

## Verify understanding

Use a short adaptive conversation to check whether the user has grasped the main ideas. This workflow is self-contained; it does not require another skill.

### Start with one question

After delivering the overview, normally append one concrete core question and mention that understanding can be checked in about 3–5 exchanges. Ask only one question at a time. Continue when the user answers; honor a request to skip, ask something else, or receive only an overview.

When asked to check an existing explanation, use that explanation instead of repeating it. Test taught core ideas and simple new situations inferable from them, not outside prerequisites.

### Check three dimensions

- **Purpose and boundaries:** explain in the user's own words what the field addresses and how it differs from an adjacent concept.
- **Relationships and causes:** explain how major parts work together, or what happens if a key part is removed and why.
- **Transfer and limits:** reason through a simple new situation, choose an approach or predict a failure, and explain the relevant condition.

Adapt questions to the subject. Do not test author names, dates, exact terminology, trivia, or untaught formulas. Accept defensible alternative classifications and wording.

### Respond to the actual answer

Do not reveal the reference answer before the user responds. Afterward, briefly identify what their answer demonstrates, isolate one important gap, and explain it with a reason or example.

- If vague, ask about one concrete situation.
- If incorrect, provide the minimum necessary explanation, then use a different example to check understanding. Avoid leading the user through repeated hints until they guess the answer.
- If correct, use a causal or transfer question to distinguish understanding from repetition.
- If the user challenges the explanation, check your own reasoning and sources first. Correct the map if needed; disagreement alone is not a learner error.

Choose the next question from observed gaps rather than traversing every branch. Usually conclude after 3–5 exchanges including follow-ups, or sooner when evidence is sufficient or the user stops. Continue further only when requested.

### Give a bounded conclusion

Conclude with what the user demonstrated, one remaining uncertainty if any, and one targeted clarification or next step. Ground feedback in their actual answers.

Say they have initially grasped the main ideas only when answers support purpose, relationships, and transfer. If a dimension was not tested, leave it unverified. Distinguish independent answers from success after hints. Do not assign a spurious numerical score or infer expertise or durable retention from a few questions.

## Avoid common failure modes

- Do not follow search-result order or a textbook table of contents as if it were the conceptual structure.
- Do not equate a list of terminology, papers, or products with understanding.
- Do not descend into formulas, APIs, implementation tuning, or minor benchmark differences before establishing why they matter.
- Do not present a single popular implementation as the definition of the field.
- Do not report only advantages; every major approach should be paired with its assumptions and failure boundary.
- Do not imply mastery from passive reading. Include synthesis, transfer, judgment, or practice.

## Compact operating formula

Use this sequence as a guide, not a rigid output template:

`problem → map → causal spine → trade-offs → representative evidence → verification → selective depth`

The desired outcome is that the user can place new information, predict likely strengths and failures, and decide where deeper study has the highest value.
