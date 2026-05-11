# DSS Advisor

A general-purpose Decision Support System (DSS) skill for Claude, grounded in four canonical DSS texts.

## What it does

Turns complex, ambiguous organizational decisions into structured decision briefs. Handles semi-structured and unstructured problems — the kind where there's no obvious playbook, multiple stakeholders have competing interests, and the stakes are high enough that gut feel isn't enough.

The skill diagnoses the problem, selects the appropriate analytical depth, and produces a structured output using PrOACT as the universal scaffold. It can also generate research briefs, stakeholder maps, tradeoff matrices, and scenario analyses.

## Theoretical Foundation

Built from four texts that collectively define the DSS field:

| Source | Contribution |
|--------|-------------|
| Keen & Scott Morton (1978) | Decision taxonomy: structured / semi-structured / unstructured. The original DSS framework. |
| Turban, Sharda & Delen (2011) | DSS systems architecture, Simon's four decision phases, DSS types, AI integration guidance |
| Goodwin & Wright (2014) | Multi-criteria decision analysis, SMART method, stakeholder tradeoff analysis, cognitive bias detection |
| Hammond, Keeney & Raiffa (1999) | PrOACT framework: Problem, Objectives, Alternatives, Consequences, Tradeoffs, Uncertainty, Risk, Linked Decisions |

## How it works

**Step 1 — Diagnose**
Scores the problem on three axes: Certainty, Stakeholders, Precedent. Sum determines analytical depth (light / standard / deep).

**Step 2 — Frame**
Applies PrOACT problem reframing before touching any alternatives. Challenges the stated problem to ensure the right decision is being solved.

**Step 3 — Analyze**
Applies MCDM stakeholder mapping and tradeoff analysis when multiple parties are involved.

**Step 4 — Output**
Produces a structured Decision Brief: problem statement, objectives, alternatives, consequences, tradeoffs, and a synthesis that supports — but does not replace — the decision maker's judgment.

## Installation

Upload `SKILL.md` to your Claude skills directory.

## Use cases

- Strategic governance decisions (e.g. AI adoption, regulatory compliance, technology risk)
- Multi-stakeholder tradeoff analysis
- Research briefs on novel or unsettled domains
- Executive decision support and scenario planning

## License

MIT
