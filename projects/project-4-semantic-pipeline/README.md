# Project 4 — Iterative OWL Reasoning and LLM Abduction

**Due:** Week 13
**Submission:** Pull request
**Purpose:** Compare deductive reasoning over an incrementally constructed OWL representation with abductive reasoning by a large language model. The project asks when a set of formally represented clues is sufficient for an OWL DL reasoner to determine who owns the zebra, and what an LLM hypothesizes before that deductive result is available.

## Overview

You will work with the classic Zebra Puzzle, sometimes called the Einstein Puzzle.

Rather than giving all of the clues to a reasoner or an LLM at once, you will **build the puzzle incrementally in OWL**.

At each stage you will:

1. represent a new group of clues in OWL;
2. run an OWL DL reasoner to determine what follows deductively;
3. determine whether the available clues are yet sufficient to entail who owns the zebra;
4. provide the current OWL representation to an LLM;
5. ask the LLM to make its **best abductive hypothesis** about who owns the zebra, while explaining:
   * what it can infer with confidence from the supplied evidence;
   * what remains underdetermined; and
   * why it nevertheless favors its current hypothesis;
6. record the result; and
7. add additional clues and repeat the process.

The experiment therefore tracks two reasoning processes in parallel:

* **Deduction:** What is actually entailed by the OWL axioms?
* **Abduction:** Given incomplete evidence, what answer does the LLM judge to be the best current explanation or hypothesis?

The goal is not merely to solve the Zebra Puzzle. The goal is to observe how abductive reasoning changes as the space of logical possibilities is progressively constrained by formally represented background knowledge.

## Part 1 — Construct the Puzzle in OWL

Use the supplied [`clue-packets/`](clue-packets/) to add the puzzle clues incrementally.

Represent the relevant entities, categories, relations, and clues in OWL. Your ontology should capture enough structure for a DL reasoner to draw the intended conclusions.

Depending on your modeling approach, this may require axioms representing such things as:

* the houses;
* their ordering or adjacency;
* the people associated with the houses;
* nationalities;
* colors;
* drinks;
* pets;
* other attributes used by the puzzle;
* uniqueness constraints;
* disjointness constraints;
* exactly-one relationships where appropriate; and
* the clues connecting these categories.

## Part 2 — Run the DL Reasoner After Each Clue Packet

After incorporating each clue packet, run an OWL 2 DL reasoner such as **HermiT**.

For each stage, determine:

1. Is the ontology consistent?
2. What new facts are entailed?
3. Can the reasoner now determine who owns the zebra?
4. If not, what possibilities remain open?
5. Does the current ontology reveal any mistakes or omissions in your formalization?

You should distinguish carefully between:

> **The ontology is consistent with X**

and

> **The ontology entails X.**

The fact that a candidate solution remains logically possible does not mean that it has been deductively established.

Continue adding clue packets until the reasoner can determine the zebra owner.

## Part 3 — Ask the LLM to Reason Abductively

After **each reasoner check**, provide the current OWL ontology to an LLM.

Ask the LLM to answer the following question:

> Based only on the ontology and clues supplied, who is your best current guess for the owner of the zebra?

The LLM should also be instructed to:

* reason only from the supplied ontology;
* not search for the Zebra Puzzle or its known solution;
* not rely on a memorized answer;
* identify what the supplied evidence actually establishes;
* distinguish established conclusions from hypotheses;
* explain why its proposed zebra owner is currently the best hypothesis; and
* acknowledge alternative possibilities where the evidence remains insufficient.

A useful prompt pattern is:

> The attached OWL ontology represents only some of the clues from a logic puzzle. Do not use prior knowledge of the Zebra Puzzle or a memorized solution. Analyze only the supplied ontology. First explain what you can infer with confidence. Then state whether the evidence deductively determines who owns the zebra. If it does not, make your best abductive guess about who owns the zebra and explain why you favor that hypothesis over the remaining alternatives.

Use substantially the same prompt at each stage so that changes in the LLM's response can be compared meaningfully.

## Part 4 — Iterate

Repeat the cycle as additional clues are added:

```text
Add clue packet
      ↓
Represent clues in OWL
      ↓
Run DL reasoner
      ↓
What is deductively entailed?
      ↓
Can the zebra owner be determined?
      ↓
Submit current OWL to LLM
      ↓
Request best abductive hypothesis
      ↓
Record hypothesis and justification
      ↓
Add next clue packet
```

Your experiment should make it possible to see how the LLM's hypothesis changes as the ontology progressively reduces the space of logical possibilities.

An especially interesting result occurs if the LLM guesses the correct answer **before** the OWL reasoner can entail it. That does not mean the LLM has deductively solved the problem. It means that, given incomplete evidence, it has selected the eventual answer as its preferred hypothesis.

Likewise, an incorrect early guess is not necessarily a failure. It provides evidence about how the model behaves when forced to reason under incomplete information.

## Part 5 — Compare the Reasoning Processes

Once the full clue set has been represented, run the DL reasoner one final time.

Your final analysis should compare the history of the LLM's hypotheses with the deductive conclusions produced by the reasoner.

At minimum, discuss:

* when the OWL reasoner first entailed the identity of the zebra owner;
* what the LLM guessed at each earlier stage;
* whether and when the LLM converged on the deductively established answer;
* which additional clues caused significant changes in the LLM's hypothesis;
* whether the LLM ever claimed greater certainty than the ontology justified;
* whether it correctly distinguished what was entailed from what it was merely hypothesizing;
* how the addition of OWL axioms progressively reduced the logical possibility space; and
* what the experiment suggests about combining formal deduction with LLM-based abductive reasoning.

## Required Artifacts

Create:

```text
submissions/YOUR-GITHUB-USERNAME/project-4/
├── run-log.md
├── ontology/
│   ├── stage-01.owl
│   ├── stage-02.owl
│   ├── stage-03.owl
│   └── ...
├── final-ontology.owl
├── llm-transcripts/
│   ├── stage-01.md
│   ├── stage-02.md
│   ├── stage-03.md
│   └── ...
└── analysis.md
```

Your `run-log.md` should provide a compact record of each iteration. For example:

| Stage | Clues Added | Reasoner Entails Zebra Owner? | LLM Hypothesis | LLM Confidence / Rationale |
| ----- | ----------- | ----------------------------- | -------------- | -------------------------- |
| 1     | Packet 1    | No                            | Person A       | ...                        |
| 2     | Packet 2    | No                            | Person C       | ...                        |
| 3     | Packet 3    | No                            | Person C       | ...                        |
| ...   | ...         | ...                           | ...            | ...                        |
| Final | All clues   | Yes: Person X                 | Person X       | ...                        |

Use the actual entities from your ontology rather than these placeholders.

## Your Analysis Must Distinguish

Your report must clearly distinguish:

* **deductive entailment** — a conclusion that follows logically from the OWL axioms;
* **consistency** — a state in which the axioms can all be true together;
* **logical possibility** — an arrangement not ruled out by the current axioms;
* **abductive hypothesis** — a proposed answer selected as the best explanation or guess given incomplete evidence;
* **LLM confidence** — the model's expressed degree of confidence, which is not itself evidence of logical entailment.

Do not treat these as interchangeable.

In particular:

> A reasoner's inability to entail an answer does not show that the answer is false.

and

> An LLM's confident prediction does not show that the answer follows deductively from the available clues.

## Evaluation

Strong work:

* represents the clues faithfully in OWL rather than encoding the known solution;
* uses an OWL DL reasoner after each significant addition of evidence;
* explicitly records what is and is not entailed at every stage;
* gives the LLM the same evolving formal representation used by the reasoner;
* prevents the LLM, as far as practicable, from relying on the memorized Zebra Puzzle solution;
* asks the LLM to distinguish certain conclusions from abductive hypotheses;
* documents changes in the LLM's hypothesis as new axioms are introduced;
* correctly distinguishes consistency, possibility, abduction, and deduction;
* identifies the point at which the formal representation becomes sufficient to determine the zebra owner; and
* uses the experiment to explain the complementary roles of formal reasoning and LLM-based hypothesis generation.

The quality of the experiment is more important than whether the LLM guesses correctly at an early stage.

## After Submission

During Week 14, submit one substantive review of another student's Project 4 pull request. Your review should pay particular attention to whether the student's OWL axioms genuinely support the deductive conclusions they report and whether their analysis keeps LLM hypotheses distinct from reasoner entailments.
