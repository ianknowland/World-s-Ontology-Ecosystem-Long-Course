# Project 4 — Run Log

Use this log to record each iteration of the experiment.

For every clue packet:

1. add the new clues to the OWL ontology;
2. run an OWL DL reasoner;
3. record what is deductively entailed;
4. determine whether the zebra owner is yet entailed;
5. submit the current OWL ontology to the LLM;
6. ask for its best abductive hypothesis; and
7. record its answer and justification.

---

## Experimental Setup

### OWL DL Reasoner

Reasoner used:

### LLM

Model used:

### Standard LLM Prompt

Paste the prompt used across iterations here.

The prompt should instruct the model to:

- reason only from the supplied OWL ontology;
- not search for the Zebra Puzzle or use a memorized solution;
- distinguish what is established from what is hypothesized;
- state whether the evidence determines the zebra owner;
- if it does not, provide its best abductive guess and explain why.

---

# Iteration 1 — Clue Packet 1

## Clues Added

List the clues introduced at this stage.

## OWL Representation

Briefly describe the principal axioms added.

OWL file:

`ontology/stage-01.owl`

## DL Reasoner Results

### Is the ontology consistent?

Yes / No

### Important new entailments

List the relevant conclusions produced by the reasoner.

### Is the zebra owner entailed?

Yes / No

If yes, identify the entailed owner.

### What remains logically possible?

Describe the alternatives that have not yet been ruled out, where this can be determined.

## LLM Abductive Reasoning

### Prompt

Record the actual prompt or link to the transcript.

### Best current hypothesis

Who does the LLM guess owns the zebra?

### What does the LLM claim is established?

Record the conclusions the LLM treats as supported by the ontology.

### Why does it favor its hypothesis?

Summarize its justification.

### Confidence

Record any confidence expressed by the LLM.

### Did it overstate what follows from the ontology?

Yes / No

Explain briefly.

---

# Iteration 2 — Clue Packet 2

Repeat the same structure used for Iteration 1.

---

# Iteration 3 — Clue Packet 3

Repeat the same structure used for Iteration 1.

---

# Iteration 4 — Clue Packet 4

Repeat the same structure used for Iteration 1.

---

# Additional Iterations

Add additional sections if more clue packets are used.

---

# Final Reasoner Check

## Final ontology

`final-ontology.owl`

## Is the ontology consistent?

Yes / No

## Is the zebra owner deductively entailed?

Yes / No

## Entailed zebra owner

Record the answer if entailed.

## Relevant entailments supporting the answer

Identify the principal conclusions produced by the reasoner.

---

# Iteration Summary

| Stage | Clues Added | Ontology Consistent? | Zebra Owner Entailed? | LLM Hypothesis | LLM Correct? | LLM Overstated Certainty? |
|---|---|---|---|---|---|---|
| 1 | Packet 1 | | | | | |
| 2 | Packet 2 | | | | | |
| 3 | Packet 3 | | | | | |
| 4 | Packet 4 | | | | | |
| Final | All clues | | | | | |

---

# Observations

## When did the LLM first guess the eventual answer?

## When did the OWL reasoner first entail the answer?

## Which added clues changed the LLM's hypothesis?

## Did the LLM ever guess correctly before the answer was deductively available?

## Did the LLM ever claim certainty that the ontology did not justify?