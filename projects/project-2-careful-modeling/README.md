# Project 2 — Careful Modeling

**Due:** Week 7  
**Submission:** Pull request  
**Purpose:** Apply a repeatable modeling process to difficult domains, make commitments explicit, encode them in OWL, write definitions, and use a reasoner.

This project adapts the careful-modeling exercises from the intensive course, where students constructed reusable design patterns, encoded them in OWL, wrote definitions and identifying descriptions, and ran a reasoner.

## Choose two cases

Complete any **two** cases from [`cases/`](cases/).

For each case:

1. state the competency question and scope;
2. construct a reusable ontology design pattern;
3. identify classes, named individuals, literal values, object-property relations, and data-property relations;
4. encode the pattern in OWL using Protégé;
5. write textual definitions for every locally created class and relation;
6. write identifying descriptions for locally created named individuals;
7. run HermiT or another OWL 2 DL reasoner; and
8. write a short modeling rationale explaining the most important decisions and alternatives rejected.

There may be more than one defensible solution. The submission must make its commitments explicit and apply them consistently.

## Definition expectations

For classes, prefer genus–differentia form:

> A [genus] that [differentia].

For relations, use a form such as:

> A relation that holds between [source] and [target] when [condition].

Definitions should define entities rather than words, avoid circularity, and agree with the OWL axioms.

## Required files

```text
submissions/YOUR-GITHUB-USERNAME/project-2/
├── case-N-pattern.png      # PDF or SVG also acceptable
├── case-N.owl
├── case-N-notes.md
├── case-M-pattern.png
├── case-M.owl
└── case-M-notes.md
```

## Resources

- [Original Day 1 patrol-boat OWL exercise](https://github.com/Applied-Ontology-Education/World-s-Ontology-Ecosystem/tree/main/exercises/day-1)
- [Original Day 2 careful-modeling exercise](https://github.com/Applied-Ontology-Education/World-s-Ontology-Ecosystem/tree/main/exercises/day-2)
- [Definition-writing guidance from the intensive course](https://github.com/Applied-Ontology-Education/World-s-Ontology-Ecosystem/blob/main/exercises/day-2/Guidelines%20for%20Writing%20Definitions.pdf)

## Evaluation

Strong work shows:

- careful separation of classes, individuals, relations, and values;
- appropriate distinctions among material entities, processes, roles, information artifacts, qualities, and measurements where relevant;
- reusable patterns rather than a diagram of a single source row;
- definitions that agree with the formal model;
- justified OWL axioms and restrictions;
- correct interpretation of reasoner results; and
- explicit discussion of difficult modeling choices.

## After submission

During Week 8, submit one substantive review of another student’s Project 2 pull request.
