# Project 1 — Ontology Use and Ecosystems

## Student

- Name: Ian Knowland
- GitHub username: ianknowland

## Problem
My wife has worked at two health insurance companies. The frequent data issues she encountered run the gamut of possibilities for this assignment, but one that kept popping up is that the knowledge bases used by clients and employees are outdated, siloed, contradictory, and not well-maintained. When you look up the policies for handling certain kinds of claims, you will get routed to a resource that is untrustworthy often enough to be a potential legal issue and raising the issue to one's supervisors would not always yield a better answer because they also rely on these flawed sources of truth. The way that the internal policies interacted with each other might send you in circles, so to speak, with no clear way forward. Provenance for changes to the knowledge bases are virtually non-existent, so attempting to figure out the point of failure and addressing it was difficult if not futile.

## Why Ontology Might Help
An ontology could provide a structured and queryable representation of knowledge base documentation, individual sections of those documents, and the kinds of claims they apply to through various relations. Versioning metadata on entities in the graph can temporally index points of informational failure; class restrictions and object property relations could support inferencing over these documents, resulting in logically-derived assertions; governance-informed SHACL shapes applied to the graph could flag violations with respect to claims and their relevant policies.

## Why Ontology Might Not Help
1. Short answer: willingness to implement correctly. The quality of the knowledge base itself is not determined by an ontology; it's only as good as the people who are responsible for making changes to the information. If a person (or AI agent) isn't re-racking how documentation entities relate to the information they govern based on updates to the knowledge base, then the graph would be useless at best and destructive at worst, given the strict legal nature of communicating insurance information to clients. Realistically, a small- to medium-sized company might prefer to offload that to an AI agent anyway without the engineering required to implement and maintain an ontology solution. The use of an ontology would require significant tooling, as the knowledge bases are sometimes scattered across different resources that might not be configured to talk to each other, even though that's the exact scenario ontologies are designed to address. Microsoft OneNote (an egregious offender), SharePoint, Word documents, PowerPoint slides, emails and chat messages, proprietary software suites, etc. Creating an ontology doesn't automatically solve this interoperability issue without reconfiguring existing architecture or engineering a new one to support it, not to mention hiring one or more ontologists and/or data scientists for long-term support, which these companies may not be willing to do.

2. Short answer: Wikis exist! It's possible to have a knowledge base that makes it easy to link information to other pieces of information, with a change log and provenance. You might be thinking, "Didn't you call out SharePoint as an issue when it's essentially a wiki?" The issue is when a tool that would serve the purpose is not utilized to greatest effect. It would be a manual effort to populate a wiki, but so is populating a knowledge graph and, arguably, a wiki is much faster on that front. They're often cheap and simple to implement, and a lot of successful companies in a variety of industries use internal wikis to organize their knowledge bases to great effect. Why engineer an ontology solution with all of the cost and effort that entails when you can do something like this?

## Scope
The scope of a health insurance information ontology would be informational entities like internal rules/procedures/guidelines and how they relate to policy information (e.g. coverage/benefits/plans/claims), customer data, and provider data, while supporting queries over content changes to document versions.

## Competency Questions

1. What internal guide describes claims of type X?
2. When did section X of document Y begin to reference plan Z?

## Ecosystem Scan

### Effort 1
**"An ontology for healthcare systems" (Goyer, et al., 2022)**
- This ontology extends Basic Formal Ontology, Information Artifact Ontology, and Ontology for Biomedical Investigations to represent the environment of Learning Health Systems which, according to this paper, document clinical data, derive knowledge from it, and modify patient care practices in light of the new knowledge.
- In terms of domain coverage, it largely supports provider elements of the HII scope above, such as healthcare facilities, the kinds of procedures that take place in them, the roles of those performing procedures, and relations that pick out the target of those procedures.
- In my mind, this would be a case of alignment or selective reuse, as there are some design decisions I might make differently but could potentially be mappable to entities here. An example is the class *populational healthcare service delivery*, which "aims at the health of a group of organisms but selects this group by specifying a common trait among them, thus characterizing a population." Now, this is a narrative description of the term rather than an Aristotelian one like others within the paper. But even so, there's an odd set of semantics in which an instance of this process is intended to have as target an object aggregate (a population) that meets specific criteria that are not spelled out here. One can imagine a combinatorial explosion of subclasses between the kinds of populational healthcare service deliveries and the kinds of populations defined by a particular trait and (according to the paper) particular location, such as the Smoking Population of Chicago; or in the specifications that prescribe the individuals that would be parts of such a number of aggregates. Perhaps the solution is more elegant than it seems to me, but I'm having trouble seeing it if so. Other than that, there are several terms I could reuse as targets/performers of procedures that claims are about.
- I would probably look for other ontologies in this domain that extend CCO, given that I'm fairly familiar with its use at this point, and looking at how they would interact with this module.

### Effort 2
**"Towards a Cyber Information Ontology" (Limbaugh, Jensen, & Beverley)**
- This general vocabulary and proposed taxonomy aims at informing ontologies that extend, among others, the Information Entities Ontology and provide a reliable model for dealing with copies of and changes to information in a cyber information management domain.
- Digital knowledge bases in a hybrid-work health insurance setting are part of the cyber information management domain.
- Given that the stated scope of the TACIO effort is that it contains terms "too general and too few to comprise an ontology of their own", I think a robust extension that extends ontologies that contain these elements is the way to go.
- I would research ontologies that extend CCO in any related domains to see if this effort has already encouraged adoption of its content. The new Cyber Ontology Foundry is probably a good start, and watching that space for any contenders, as well as upcoming major version updates on CCOs roadmap.

### Effort 3

-
-
-
-
## Recommendation

**PROCEED / PROCEED WITH CONDITIONS / DO NOT PROCEED**

### Rationale

## AI Use

Describe any substantive AI assistance, or write `None`.