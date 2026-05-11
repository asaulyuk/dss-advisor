---
name: dss-advisor
description: >
  General-purpose DSS advisor grounded in Keen & Scott Morton (1978), Turban et al. (2011),
  Goodwin & Wright (2014), and Hammond/Keeney/Raiffa PrOACT (1999). Use whenever a user
  presents a complex, ambiguous, or high-stakes decision — especially semi-structured or
  unstructured problems involving stakeholder tradeoffs, governance, or strategic uncertainty.
  Triggers: "help me decide," "should we," "weigh the options," "what are the tradeoffs,"
  "how do I think through this," or any organizational/strategic decision framing. Also
  triggers for: competing objectives, multiple stakeholders, novel domains with unclear
  precedent, AI governance questions, or regulatory ambiguity. Produces a structured decision
  brief via PrOACT scaffold with variable analytical depth. Also supports: case studies,
  stakeholder maps, tradeoff matrices, scenario analysis, and research briefs.
---

# DSS Advisor

A decision support skill grounded in four DSS bibles. This skill does not generate answers — it
structures the conditions under which good answers become findable. The computer (Claude) is
subordinate to the decision context. The human is always in control.

---

## Core Principle (Keen & Scott Morton)

A DSS is a **service, not a product**. It must evolve with the user's understanding. Start from
the decision maker's activities and work backward to the support. Never impose structure, solutions,
or a mode of analysis. The goal is to extend the decision maker's own capabilities — not replace
their judgment.

---

## Step 1 — Receive and Diagnose the Problem

Before touching any framework, understand the problem as stated. Then score it on three axes:

```
CERTAINTY      [1–5]   How much is known about outcomes?
                       1 = no precedent, volatile environment
                       5 = well-modeled, outcomes predictable

STAKEHOLDERS   [1–5]   How many parties with competing interests?
                       1 = single decision maker, aligned interests
                       5 = multiple organizations, conflicting objectives

PRECEDENT      [1–5]   How much prior experience or doctrine exists?
                       1 = novel domain, no established rules
                       5 = well-established process, lots of case history
```

Sum the three scores. This determines analytical depth — not framework selection.

| Score | Decision Class | Depth |
|-------|---------------|-------|
| 3–6   | Structured | Light: model-based analysis, PrOACT core only |
| 7–10  | Semi-structured | Standard: full PrOACT + MCDM stakeholder layer |
| 11–15 | Unstructured | Deep: full PrOACT + MCDM + scenario analysis + psychological traps |

> **Reference:** Load `references/keen-morton.md` for decision classification guidance and
> organizational context framing. The K&SM structured/semi-structured/unstructured taxonomy is
> the canonical input here.

---

## Step 2 — Frame the Problem (PrOACT)

PrOACT is **always** the output scaffold, regardless of decision class. What changes is the depth
of each section.

The eight PrOACT elements (Hammond, Keeney, Raiffa):

| Element | Question | Depth by Class |
|---------|----------|----------------|
| **Problem** | Are we solving the right problem? | All classes — non-negotiable |
| **Objectives** | What does success actually require? | All classes |
| **Alternatives** | Have we found the full solution space? | All classes |
| **Consequences** | What happens under each alternative? | All classes |
| **Tradeoffs** | Where do objectives conflict? | Standard + Deep |
| **Uncertainty** | What could change the picture? | Deep only (unless flagged) |
| **Risk Tolerance** | How much variance is acceptable? | Deep only |
| **Linked Decisions** | What does this lock in or foreclose? | Deep only |

> **Reference:** Load `references/proact.md` for full PrOACT step-by-step protocols, reframing
> techniques, and psychological trap warnings.

**Critical problem-framing rule:** The way a decision is stated at intake often reflects the
trigger, not the real problem. Always challenge the frame before proceeding. Ask:
- What triggered this decision?
- Are the constraints in the statement assumed or real?
- Is this the right scope — too narrow? too broad?

---

## Step 3 — Map Stakeholders and Criteria (MCDM Layer)

Apply when Stakeholders score ≥ 3 (Standard or Deep class).

Using SMART (Simple Multi-Attribute Rating Technique) from Goodwin & Wright:

1. **Identify all stakeholders** — those who decide, those affected, those who can block
2. **Elicit objectives per stakeholder** — what does each party actually want?
3. **Attribute each objective** — make it measurable or at least rankable
4. **Weight the attributes** — relative importance (swing weighting preferred over direct rating)
5. **Score alternatives** on each attribute
6. **Compute weighted scores** — but treat as inputs to judgment, not as the verdict

**Tradeoff handling:** Use even-swap method (HKR) — "How much of X would you give up to gain
one unit of Y?" Makes implicit tradeoffs explicit and negotiable.

**Bias flags to surface before scoring** (Goodwin & Wright):
- Recognition heuristic (choosing what's familiar, not what's best)
- Lexicographic trap (optimizing on one attribute while ignoring others)
- Satisficing (stopping search too early)
- Reason-based choice bias (post-hoc rationalization driving the selection)

> **Reference:** Load `references/goodwin-wright.md` for full SMART protocol, attribute weighting
> methods, group decision support techniques, and bias detection checklist.

---

## Step 4 — Model Alternatives (Turban DSS Layer)

Determine which DSS *type* is most relevant to the decision at hand. This shapes what kind of
support output is most useful:

| DSS Type | Best for | Output |
|----------|----------|--------|
| **Model-driven** | Quantifiable tradeoffs, optimization | Scenario tables, sensitivity analysis |
| **Data-driven** | Signal-based decisions, BI-style | Data summary, pattern identification |
| **Knowledge-driven** | Novel domain, rule-based guidance | Rule extraction, analogical cases |
| **Document-driven** | Regulatory or compliance decisions | Evidence map, precedent summary |
| **Communications-driven** | Group decisions, multi-stakeholder | Stakeholder alignment map |

> **Reference:** Load `references/turban.md` for Simon's intelligence–design–choice–implementation
> phases, DSS component architecture, and AI integration guidance.

---

## Step 5 — Produce the Decision Brief

The output is always a structured **Decision Brief** using PrOACT as the skeleton. Calibrate
depth per Step 1 scoring.

```
## Decision Brief: [Problem Title]

### Problem Statement
[Refined problem after reframing exercise]
[Decision class: Structured / Semi-structured / Unstructured]
[Axis scores: Certainty X | Stakeholders X | Precedent X]

### Objectives
[List — primary and secondary, flagging any that conflict]

### Alternatives
[Minimum 3. Include a "do nothing" alternative. Flag any creative alternatives
that reframe the problem.]

### Consequences
[Per alternative: what happens? Use a table when >3 alternatives × >3 criteria]

### Tradeoffs
[Where objectives conflict. Use even-swap framing where possible.]

### Uncertainty  [if applicable]
[Key unknowns. Probability language only when data supports it; otherwise
use High/Medium/Low with explicit assumptions.]

### Risk Tolerance  [if applicable]
[Stakeholder appetite for variance. What failure is tolerable? What is not?]

### Linked Decisions  [if applicable]
[What does choosing each alternative lock in or foreclose downstream?]

### Recommendation
[Synthesis — not the model's answer, but the structured case for the decision
maker's judgment. State explicitly what the model cannot resolve and why
judgment is required there.]
```

---

## Additional Outputs This Skill Supports

- **Case study generation**: Real or hypothetical decision cases structured through the DSS framework
- **Stakeholder map**: Visual-ready representation of objectives and conflicts
- **Tradeoff matrix**: Weighted multi-criteria scoring table
- **Scenario analysis**: Structured uncertainty modeling (Deep class decisions)
- **Research brief**: Literature-grounded analysis of a domain (e.g., AI in cyber insurance)
- **Precedent scan**: Analogous cases from other industries or contexts

For research briefs and precedent scans, the skill applies the same diagnostic rigor — structuring
external evidence through the PrOACT lens rather than narrating it raw.

---

## Reference Files

Load only what the decision class requires:

| File | Load when |
|------|-----------|
| `references/keen-morton.md` | Always — decision classification and org context |
| `references/proact.md` | Always — PrOACT scaffold and problem reframing |
| `references/goodwin-wright.md` | Stakeholders ≥ 3 or explicit tradeoff analysis requested |
| `references/turban.md` | Model selection, AI integration, Simon's phases needed |
-e 

---

# Keen & Scott Morton — Decision Support Systems: An Organizational Perspective (1978)

## Core Contribution
The foundational DSS text. Established that computers should serve managers' *effectiveness*
(quality of decision outcomes), not just organizational *efficiency* (cost and speed). The
entire DSS field descends from this distinction.

---

## The Structured / Semi-Structured / Unstructured Taxonomy

Adapted from Simon (1960) — the most-used classification in DSS literature.

**Structured decisions**
- Rules can be fully specified in advance
- Process can be delegated to a system or a clerk
- Examples: credit scoring, inventory reorder, tax calculation
- DSS role: automate or validate

**Semi-structured decisions**
- Some components are modelable; others require judgment
- Formal analysis helps but cannot replace experience
- Examples: portfolio management, pricing strategy, vendor selection
- DSS role: support the judgment; make the structured components explicit

**Unstructured decisions**
- No agreed procedure exists; problem is "fuzzy"
- High reliance on intuition, experience, and context
- Examples: mergers & acquisitions, entering a new market, responding to a regulatory shift
- DSS role: extend the decision maker's ability to search, evaluate, and scenario-test

> **Key insight for classification:** Problems migrate over time. What was unstructured in 1975
> (credit scoring) became structured by 1990 as understanding deepened. The AI/insurance
> ambiguity problem is currently unstructured — there is no established doctrine. A DSS here
> must be designed to evolve, not to deliver a fixed answer.

---

## Efficiency vs. Effectiveness

| Dimension | Efficiency | Effectiveness |
|-----------|-----------|---------------|
| Focus | Cost, speed, error rate | Quality of decision outcomes |
| Who benefits | Operations | Senior management |
| What it addresses | Programmable tasks | Fuzzy, strategic problems |
| Computer's role | Replace clerical work | Extend managerial judgment |

The Megabuck Trust example: operational systems got maximally efficient by 1972. No further
efficiency gain was possible. A 0.25% improvement in investment *effectiveness* was worth
$500,000 more than any further efficiency gain. This is why DSS exists.

---

## The Four DSS Principles

1. **The computer is subordinate to context.** System design must start from the manager's
   decision activities, not from what the technology can do.

2. **A DSS is a service, not a product.** Since problems are only partially structured and
   understanding evolves, a DSS must grow and adapt. "Signing off" on a finished system is
   the wrong model.

3. **Support, not replace.** The decision maker retains full control. A system that imposes
   structure, solutions, or a mode of analysis will not be used.

4. **Mesh with organizational constraints.** The DSS cannot be built in isolation from the
   political, structural, and cultural context in which decisions are made.

---

## Organizational Context Framing

Before applying any decision framework, map the organizational setting:

- **Who owns the decision?** (authority, accountability)
- **Who is affected?** (stakeholders, downstream parties)
- **What are the organizational constraints?** (reporting relationships, performance metrics,
  political pressures, regulatory requirements)
- **What information-processing capacity does the decision maker have?** (bounded rationality)
- **What systems are already in use?** (legacy behavior, embedded heuristics)

---

## Application to Novel/Unstructured Problems

When a problem has no established doctrine (like AI in cyber insurance):

1. Identify the *components* that can be structured (known regulations, documented exclusions,
   historical breach data, comparable industries)
2. Isolate the *fuzzy core* (how insurers will evolve underwriting criteria, what "AI involvement"
   will mean contractually, regulatory direction)
3. Design the DSS to support iteration — the goal is not to produce a one-time answer but to
   make the decision maker progressively better-informed as the domain clarifies
4. Treat the first brief as a stake in the ground to be revised, not a verdict
-e 

---

# Hammond, Keeney, Raiffa — Smart Choices: PrOACT Framework (1999)

## Core Contribution
The most actionable decision-structuring methodology for non-technical stakeholders. PrOACT
is the standard by which complex decisions are made manageable. The approach is proactive —
seek decision opportunities rather than wait for problems to force choices.

The effective decision-making process must: focus on what's important, be logical and consistent,
acknowledge both subjective and objective factors, require only the analysis necessary, encourage
relevant information gathering, and be straightforward, flexible, and reliable.

---

## The Eight PrOACT Elements

### 1. Problem — Define the right decision problem

The way a problem is framed determines everything downstream. Framing errors compound.

**Problem-framing protocol:**
1. Identify the trigger — what initiated this decision?
2. Challenge the constraints — which are assumed vs. real?
3. Identify all implied sub-decisions (what does this hinge on? what does it foreclose?)
4. State the problem at multiple scope levels (narrow, medium, broad)
5. Pick the scope that captures the real decision, not the surface symptom
6. Revisit throughout — reframing opportunities often emerge mid-process

**Common framing traps:**
- Solving the presenting problem instead of the underlying one
- Accepting constraints as fixed when they're negotiable
- Treating a symptom as the decision (the renovation/moving example: "How do we renovate?"
  was not the decision — "How do we get enough room?" was)
- Letting the trigger determine the frame (trigger = "insurer denied claim" ≠ problem =
  "what is our governance model for AI deployment?")

---

### 2. Objectives — Clarify what success actually requires

Objectives are decision criteria. Without a full set, any alternative will satisfy some objectives
while silently failing others.

**Objectives protocol:**
1. Write down all concerns, unconstrained — no filtering yet
2. Separate means-objectives (getting a bigger office) from ends-objectives (productive work,
   status signaling, collaboration)
3. Focus on ends-objectives — means can always change; ends are what matter
4. Make objectives specific enough to evaluate alternatives against them
5. Flag objectives that conflict — this is where tradeoffs live

**Warning:** Hard (quantitative) objectives tend to crowd out soft (qualitative) ones. Short-term
objectives tend to crowd out long-term ones. Explicitly protect both.

---

### 3. Alternatives — Create the full solution space

Decision quality is bounded by the quality of the best alternative considered. A great analysis
of a bad alternative set is still a bad decision.

**Alternatives protocol:**
1. Always include a "do nothing / status quo" alternative — makes real costs visible
2. Force at least one creative alternative that reframes the problem
3. Ask: what would we do if the obvious option were unavailable?
4. Ask: what would a decision maker from a different industry choose?
5. Avoid collapsing distinct options into a single "hybrid" prematurely

---

### 4. Consequences — Describe outcomes honestly

For each alternative, map what actually happens across each objective.

**Consequences protocol:**
1. For each alternative × objective cell: describe the outcome in concrete terms
2. Use ranges when outcomes are uncertain — avoid false precision
3. For high-stakes cells, trace the causal chain (if we choose A, then X happens, which leads
   to Y, which affects Z)
4. Surface hidden consequences — second-order effects, stakeholder reactions, lock-ins

**Table format for ≥3 alternatives, ≥3 objectives:**
```
              | Objective 1 | Objective 2 | Objective 3 |
Alternative A |             |             |             |
Alternative B |             |             |             |
Alternative C |             |             |             |
```

---

### 5. Tradeoffs — Make competing objectives explicit

Most complex decisions have no perfect alternative. The task is to choose intelligently among
imperfect options. Tradeoff analysis makes implicit choices explicit.

**Even-swap method:**
"How much of X would I give up to gain one unit of Y?"

Example: "I would accept $50,000 less in annual revenue to reduce compliance risk by one
tier" — this makes the tradeoff concrete and auditable.

Steps:
1. Identify the pair of conflicting objectives
2. Anchor one: how much of this are you willing to sacrifice?
3. Express the tradeoff as a ratio
4. Apply consistently across all alternative comparisons

**Warning:** Tradeoffs should be explicit, not buried in intuitive synthesis. If a decision maker
cannot articulate the tradeoff, they are making it unconsciously — which is where bias enters.

---

### 6. Uncertainty — Confront what you don't know

Apply when Certainty score ≤ 3 (see SKILL.md diagnostic).

**Uncertainty protocol:**
1. List all key uncertainties affecting the decision
2. Rate each: High / Medium / Low likelihood of materializing
3. Rate each: High / Medium / Low impact on outcomes if it does
4. For High-High cells: design the alternative that is most robust to this uncertainty
5. Distinguish uncertainty (unknown likelihood) from risk (known likelihood, uncertain outcome)

**In novel domains (like AI/insurance ambiguity):** The primary uncertainties are often
*definitional* — what will "AI involvement" mean to insurers in 3 years? This class of uncertainty
requires scenario planning (see Goodwin & Wright reference) not just probability assignment.

---

### 7. Risk Tolerance — Know the decision maker's appetite for variance

Apply in combination with uncertainty analysis for high-stakes decisions.

**Questions to surface risk tolerance:**
- What is the worst acceptable outcome (floor)?
- What is required for the decision to be considered successful (threshold)?
- Is the decision maker risk-seeking (prefers high variance, asymmetric upside) or
  risk-averse (prefers predictable outcomes, lower ceiling but higher floor)?
- Are there organizational constraints on risk tolerance that override personal preference?

---

### 8. Linked Decisions — Plan ahead by sequencing choices

Many important decisions are linked. Choosing today narrows the option space for tomorrow.
Failing to account for future decisions often leads to near-term optimization that forecloses
longer-term options.

**Linked decision protocol:**
1. Identify what this decision locks in (sunk cost, contractual commitment, relationship signal)
2. Identify what options it preserves (reversibility, option value)
3. Identify what decisions *follow from* this one and when
4. Ask: should we delay this decision to gather information that would change it?
5. Design for reversibility where the cost of reversal is low

---

## Psychological Traps (Chapter 10)

The most common cognitive errors in decision making. Check these before finalizing any brief.

| Trap | Description | Counter-move |
|------|-------------|-------------|
| **Anchoring** | First information received biases all subsequent judgment | Deliberately generate an independent estimate before reviewing any data |
| **Status quo bias** | Overvaluing current state due to loss aversion | Force explicit comparison: what would you choose if starting fresh? |
| **Sunk cost trap** | Past investments influence forward-looking choices | Ask: "If we hadn't already spent X, what would we choose now?" |
| **Confirming evidence** | Seeking data that supports the preferred option | Assign someone to argue the opposing case seriously |
| **Framing effect** | Same facts presented differently produce different choices | Restate the problem multiple ways; check if the choice changes |
| **Overconfidence** | Underestimating uncertainty in own estimates | Ask for 90% confidence intervals, then widen them |
| **Availability** | Recent or vivid events receive disproportionate weight | Check: is this event representative, or just memorable? |

---

## PrOACT Quick Reference Card

```
P — Problem:       Am I solving the right problem?
r — (linking)
O — Objectives:    What does success actually require?
A — Alternatives:  Have I found the full solution space?
C — Consequences:  What actually happens under each alternative?
T — Tradeoffs:     Where do objectives conflict, and what am I willing to give up?

[For high-stakes or uncertain decisions:]
U — Uncertainty:   What could change the picture?
R — Risk:          How much variance am I willing to accept?
L — Linked:        What does this foreclose or enable downstream?
```
-e 

---

# Goodwin & Wright — Decision Analysis for Management Judgment (2014)

## Core Contribution
Practical multi-criteria decision analysis. The authoritative text on how to structure decisions
with multiple stakeholders and competing objectives. Provides both the theory (why intuitive
tradeoff methods fail) and the tools (SMART, swing weighting, even-swap) for compensatory
decision making.

---

## The Fundamental Problem with Intuitive Multi-Criteria Decisions

Research shows decision makers use cognitive shortcuts (heuristics) that are fast but produce
systematically biased results. The critical insight: most intuitive strategies are **non-compensatory**
— they evaluate criteria independently rather than allowing strength on one to offset weakness
on another. MCDM methods force the compensatory reasoning that good decisions require.

---

## Common Decision Heuristics (and Why They Fail)

| Heuristic | How it works | When it fails |
|-----------|-------------|---------------|
| **Recognition** | Choose the option you recognize | Recognition ≠ quality; rewards familiarity bias |
| **Lexicographic** | Optimize on the most important attribute; use others only to break ties | Ignores all non-dominant attributes; non-compensatory |
| **Satisficing** | Choose the first option that meets all minimum thresholds | Stops search too early; the best option may appear later |
| **Elimination by aspects** | Eliminate options below threshold on most important attribute | Eliminates options that are close on one attribute but superior on others |
| **Reason-based choice** | Choose the option easiest to justify to others | Framing-sensitive; post-hoc rationalization drives selection |

**Warning for group decisions:** In a multi-stakeholder setting, these heuristics can interact — 
different parties using different heuristics on the same decision will produce irreconcilable
positions that look principled but are really heuristic artifacts.

---

## SMART Method (Simple Multi-Attribute Rating Technique)

The core MCDM tool for management decisions. Compensatory, structured, tractable.

### Step 1: Identify Objectives and Attributes

- An **objective** is what you want to achieve (maximize revenue stability)
- An **attribute** is how you measure it (variance in quarterly revenue)
- Every objective must have at least one measurable attribute
- Distinguish: is this attribute natural (direct measurement) or constructed (custom scale)?

### Step 2: Identify Alternatives

List all viable options. Include the status quo. Don't eliminate alternatives before scoring them.

### Step 3: Score Alternatives on Each Attribute

- Use the attribute's natural range to define a 0–100 scale
- 0 = worst plausible performance on this attribute
- 100 = best plausible performance on this attribute
- Score each alternative proportionally within this range

### Step 4: Assign Weights to Attributes

**Swing weighting protocol (preferred):**
1. Describe a hypothetical "worst alternative" that scores 0 on every attribute
2. Ask: "If this alternative could be 'swung' from 0 to 100 on exactly ONE attribute,
   which swing would provide the most value?"
3. Assign that attribute a weight of 100
4. Ask: "Which swing is next most valuable?" Assign relative weight
5. Continue until all attributes are weighted
6. Normalize weights to sum to 1

**Why direct rating fails:** People assign similar weights to all attributes regardless of actual
importance, because the range isn't salient. Swing weighting forces acknowledgment of scale.

### Step 5: Compute Weighted Scores

For each alternative:  
`Score = Σ (weight_i × score_i)` across all attributes

### Step 6: Interpret — Not as a Verdict, but as Input to Judgment

SMART scores are analytical inputs, not decisions. After computing:
- Check sensitivity: does the ranking change if a weight shifts ±20%?
- Check dominance: is any alternative clearly inferior on every attribute?
- Check value gaps: are the top-ranked alternatives close enough that qualitative factors matter?

---

## Tradeoff Analysis: The Even-Swap Method

When two alternatives score similarly overall but in different ways, an explicit tradeoff is
required. Even-swap makes this concrete:

1. Identify the attribute where Alternative A outperforms B
2. Ask: "How much of attribute X would I give up in A to match A and B on attribute Y?"
3. Make the trade until alternatives are equivalent on one attribute
4. The remaining difference determines the choice

This converts qualitative conflicts ("we want both security and speed") into explicit, auditable
tradeoffs ("we accept 15% slower deployment to reduce incident probability by 30%").

---

## Stakeholder Mapping for Group Decisions

When multiple parties are involved (Stakeholders score ≥ 3):

### Stakeholder Identification
- **Decision authorities**: who signs off?
- **Implementers**: who executes the decision?
- **Affected parties**: who bears the consequences?
- **Blockers**: who can veto, resist, or slow implementation?

### Objectives Elicitation per Stakeholder
- Conduct separately before group synthesis (avoids anchoring to loudest voice)
- Ask each party: "What would make this decision successful for you?"
- Surface hidden objectives — what won't be stated publicly?
- Identify objectives that are in genuine conflict vs. those that merely appear to conflict

### Aggregating Group Preferences
- Avoid simple averaging — hides conflict rather than resolving it
- Surface the conflict explicitly: "Party A prioritizes X; Party B prioritizes Y"
- Identify Pareto improvements — changes that benefit one party without harming another
- Use negotiation analysis (Raiffa) for zero-sum tradeoffs

---

## Scenario Planning Integration (for Deep Class Decisions)

When Certainty score ≤ 2 (very low), MCDM alone is insufficient. Combine with scenario planning:

1. Identify the 2 most critical uncertainties driving outcomes
2. Build a 2×2 scenario matrix (axes = high/low on each uncertainty)
3. Score each alternative under each of the 4 scenarios
4. Look for "robust" alternatives — those that perform acceptably across all scenarios
5. Avoid alternatives that are optimal in one scenario but catastrophic in another

**For the AI/insurance problem:** Uncertainties might be (1) speed of regulatory clarity and
(2) degree of insurer exclusion breadth. Each quadrant produces different optimal governance
postures for an AI-deploying organization.

---

## Cognitive Bias Checklist for MCDM

Before finalizing any multi-criteria analysis, check:

- [ ] Have all relevant attributes been included, including soft/qualitative ones?
- [ ] Were weights assigned using swing weighting (not direct rating)?
- [ ] Does the score distribution reflect genuine attribute ranges, not narrow anchoring?
- [ ] Were alternatives scored independently before being compared?
- [ ] Has at least one "creative" alternative been included (not just obvious options)?
- [ ] Has the reason-based choice trap been controlled for (did analysis drive the ranking,
      or did the preferred answer come first and the analysis follow)?
- [ ] For group decisions: were objectives elicited separately before aggregation?
-e 

---

# Turban, Sharda, Delen — Decision Support and Business Intelligence Systems (2011, 9e)

## Core Contribution
The most comprehensive DSS systems framework. Covers Simon's decision-making phases,
DSS component architecture, AI integration, group support, and the BI/analytics stack.
The standard graduate-level DSS textbook.

---

## Simon's Four Phases of Decision Making

The foundational model of how decisions are made. A DSS should support all four phases.

```
1. INTELLIGENCE
   Scanning the environment for decision triggers.
   Finding, identifying, and defining the problem.
   Output: A well-defined problem statement.

2. DESIGN
   Generating and analyzing possible courses of action.
   Building and testing models of alternatives.
   Output: A structured option space with evaluated alternatives.

3. CHOICE
   Selecting an alternative based on criteria.
   Sensitivity analysis, tradeoff resolution.
   Output: A recommended course of action.

4. IMPLEMENTATION
   Executing the choice and monitoring results.
   Adapting the decision as feedback arrives.
   Output: Action taken; feedback loop established.
```

**Key insight:** Many failed organizational decisions are not failures of Choice — they are
failures of Intelligence (problem not found or poorly defined) or Implementation (decision
made but never translated into action with accountability). A DSS should trace all four phases,
not just model the alternatives.

---

## DSS Types Classification (AIS SIGDSS)

| Type | Primary mechanism | Best for | Typical output |
|------|------------------|----------|----------------|
| **Model-driven** | Optimization, simulation, financial models | Quantifiable tradeoffs, resource allocation | Scenario tables, sensitivity analysis, optimization outputs |
| **Data-driven** | OLAP, data warehousing, BI querying | Signal detection, performance monitoring | Dashboards, reports, trend analysis |
| **Knowledge-driven** | Rules, expert systems, AI inference | Novel domains, regulatory compliance, classification | Recommendations, rule outputs, analogical cases |
| **Document-driven** | Text retrieval, knowledge management | Regulatory decisions, precedent research | Evidence maps, document summaries |
| **Communications-driven** | Groupware, collaboration tools | Multi-stakeholder decisions, group consensus | Meeting support, shared workspaces |
| **Compound** | Hybrid of two or more above | Complex strategic decisions | Combined output from multiple modules |

**Selection guide for the Netswitch/AI-insurance problem:**
- Insurance exclusion analysis → Document-driven (regulatory text, policy language)
- Comparative industry analysis → Data-driven (breach frequency, claim outcomes)
- AI governance framework → Knowledge-driven (rules, thresholds, documentation standards)
- CEO advisory brief → Compound (all of the above, synthesized into a structured recommendation)

---

## Key DSS Characteristics (Turban's 14)

A well-designed DSS:

1. Supports semi-structured and unstructured decisions (not just programmable ones)
2. Supports all managerial levels (not just analysts)
3. Supports both individuals and groups
4. Supports interdependent and sequential decisions
5. Covers all four of Simon's phases
6. Accommodates multiple decision styles and processes
7. Is adaptive — can be modified as user understanding grows
8. Has a high-quality, accessible user interface
9. Improves *effectiveness*, not just efficiency
10. Keeps the decision maker in full control
11. Allows end users to build and modify elements
12. Uses models as the differentiating element (vs. MIS, which only reports)
13. Accesses diverse data types (structured, unstructured, multimedia)
14. Can operate stand-alone or distributed across an organization

---

## DSS vs. BI — Practical Distinction

| | DSS | BI / Business Analytics |
|--|-----|------------------------|
| **Built for** | Specific decision problem | Broad reporting / monitoring |
| **Has own** | Database + model layer | Data warehouse |
| **Strength** | Decision structure | Pattern detection |
| **Model use** | Central | Peripheral (evolving) |
| **Output** | Recommendation or brief | Report or dashboard |

For strategic advisory work, a DSS framing is almost always more appropriate than a BI framing.
BI tells you what happened. DSS helps you decide what to do about it.

---

## AI Integration Guidance (Turban Ch. 11-13)

When AI is involved in the decision itself (as both a subject and a tool):

**AI as subject** (decisions *about* AI deployment):
- Treat the AI system as an alternative to be evaluated, not an assumption
- Map the AI's decision role: classifying, recommending, automating, or augmenting?
- Flag regulatory sensitivity: UDAAP, FCRA, EU AI Act tiers, CFPB guidance
- Document the AI's training data, model type, and auditability before governance decisions
- Build the governance framework *before* deployment, not after (the Netswitch situation
  illustrates what happens when the sequence is reversed)

**AI as tool** (using AI to support the DSS process):
- AI narrates and structures; the decision maker evaluates
- AI should not generate the weighting or the verdict in MCDM — that is the decision maker's
  judgment
- AI is well-suited to: consequence mapping, scenario generation, precedent research,
  document synthesis
- AI is poorly suited to: risk tolerance assessment, stakeholder value elicitation, final choice

**Knowledge-driven DSS and rules:**
- Expert systems encapsulate domain rules as IF-THEN logic
- Useful when domain knowledge can be codified (insurance underwriting criteria, compliance rules)
- Breaks down when rules themselves are unsettled (current AI/insurance state)
- The gap between "rules exist" and "rules are settled" is where this DSS skill operates

---

## Bounded Rationality and Its Implications (Simon)

Decision makers do not maximize — they *satisfice*. They use simplified models of the real
situation ("the model in the decision maker's head") that are necessarily incomplete.

A DSS should:
- Extend the decision maker's model, not replace it
- Make the simplifications in the model visible
- Flag where the simplified model diverges from full-information analysis
- Never claim to eliminate bounded rationality — only to manage it

For organizational decisions: organizational context adds further constraints on rationality.
Political pressures, performance metrics, reporting structures, and legacy commitments all
shape what a decision maker can actually choose, regardless of what analysis recommends.
Always account for this before finalizing a recommendation.

---

## Implementation Phase — The Most Neglected Phase

Most DSS failures are not analytical failures — they are implementation failures. Decision briefs
that do not address implementation are only half-complete.

Minimum implementation section for any decision brief:
1. Who is accountable for executing this decision?
2. What is the decision timeline and key milestones?
3. What feedback mechanisms will confirm whether the decision is working?
4. What are the early warning signals that the decision needs to be revisited?
5. What decisions become available (or unavailable) once implementation begins?
