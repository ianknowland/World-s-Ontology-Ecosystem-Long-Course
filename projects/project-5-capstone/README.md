# Project 5 — Capstone Synthesis

**Due:** Week 15   
**Submission:** Pull request
**Purpose:** The capstone brings together the main themes of the course:

- ontology tradecraft;
- careful modeling and reusable design patterns;
- definitions;
- OWL and reasoning;
- critical use of large language models;
- ontology-enabled applications; and
- the difference between preserving meaning and merely moving data.

The goal is not to build a large ontology. Keep the model small, clear, and defensible.

## Scenario

A maintenance procedure specifies that a pump should be inspected every 30 days.

Technician Alex performs **Inspection 17** on **Pump P-17**. The inspection produces **Report R-17**. The report records a vibration measurement of **4.2 mm/s** and states that the pump requires bearing replacement. **Work Order W-22** requests that replacement.

## Part 1 — Build the pattern and OWL model

Aim for approximately:

- 5–10 classes;
- 3–5 relations;
- the named individuals in the scenario;
- relevant literal values; and
- at least 3 textual definitions.

Distinguish classes, named individuals, relations, literal values, processes, roles, information artifacts, and qualities or measurements where relevant.

Your model should make it possible to determine:

1. What is the inspection procedure?
2. Who performed Inspection 17?
3. What was inspected?
4. What information resulted from the inspection?
5. What vibration value was recorded?
6. What maintenance action was requested?
7. Which work order requests that action?

## Part 2 — Definitions

Write at least three definitions for important classes or relations. Definitions must agree with the OWL model.

## Part 3 — AI comparison

Ask an LLM to model the same scenario. Identify at least three meaningful differences between its proposal and yours. For each, decide:

- **ACCEPT**
- **REJECT**
- **MODIFY**

Then defend the decision.

## Part 4 — Reasoner

Run an OWL reasoner and record:

- consistency;
- unsatisfiable classes;
- expected classifications;
- unexpected inferences; and
- problems the reasoner cannot adjudicate.

## Part 5 — Operational view

Imagine an application displays only:

```text
Pump: P-17
Last inspection: Inspection 17
Measured vibration: 4.2 mm/s
Maintenance action: Replace bearing
Work order: W-22
```

For each field, identify the ontology source. Then explain what information was omitted and whether the operational view is **lossy**, **divergent**, both, or neither.

## Part 6 — Capstone synthesis statement

Write approximately **750–1,000 words** that connects the model to the broader course. Your synthesis must:

1. identify the most important modeling commitment you made;
2. explain how ontology tradecraft constrained your formalization;
3. explain what automated reasoning did and did not establish;
4. evaluate the role of the LLM in the project;
5. explain what semantic content is lost in the operational view; and
6. defend your position on at least one disputed issue raised in the Smith–Beverley debates about the future or practice of ontology engineering.

## Required files

```text
submissions/YOUR-GITHUB-USERNAME/project-5/
├── capstone-model.owl
├── capstone-pattern.png       # PDF/SVG acceptable
└── capstone-notes.md
```

Use [`capstone-notes-template.md`](capstone-notes-template.md).

## Evaluation

Because this is the capstone, the emphasis is on integration and judgment rather than ontology size. Strong work demonstrates that the student can connect conceptual analysis, formal modeling, automated reasoning, AI use, operational representations, and professional ontology-engineering tradeoffs into one defensible solution.
