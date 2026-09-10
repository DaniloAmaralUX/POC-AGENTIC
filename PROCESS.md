# Canonical POC Process

**Process version:** v1.0  
**Status:** living standard  
**Last updated:** 2026-09-10

This file is the canonical method. If the POC process evolves, update this file first and record the change in `CHANGELOG.md`.

## Purpose

Transform incomplete, ambiguous or stakeholder-led material into the smallest credible product experience that can be designed, built and inspected without converting uncertainty into fake certainty.

This process is optimized for a common operating constraint: the POC team may receive only PDFs, transcripts, briefs, screenshots, existing-system material and technical documentation, with **no direct access to the client or end user**.

The process therefore distinguishes:

- evidence extraction;
- requirements engineering;
- product/design hypothesis;
- verification;
- real user validation.

A POC may be strong without direct user access. It must not claim to be user-validated when that access did not exist.

---

# Core model

```text
SOURCE
  ↓
CLAIM
  ↓
FACT / INFERENCE / ASSUMPTION / QUESTION
  ↓
DOMAIN + OPERATIONAL MODEL
  ↓
REQUIREMENT
  ↓
POC HYPOTHESIS
  ↓
IA + TASK FLOW
  ↓
PROTOTYPE / FRONT-END
  ↓
VERIFICATION / INSPECTION
  ↓
LEARNING
  ↓
PROCESS UPDATE
```

Supporting specification: `EVIDENCE-TO-REQUIREMENTS.md`.

---

## Phase 0 — Intake and Source Manifest

### Goal
Understand what material actually exists before interpreting it.

### Inputs
Examples:
- stakeholder meetings/transcripts;
- briefs and requirement lists;
- screenshots;
- existing systems;
- technical documentation;
- analytics/support material when provided;
- regulations;
- competitor/reference material;
- user research, if available.

### Agent actions
1. Read the complete available corpus.
2. Assign a stable ID to every source.
3. Record source type, perspective, date/version and limitations.
4. Distinguish project evidence from external research.
5. Record missing/garbled sections.
6. Do not resolve contradictions silently.

### Output
Source Manifest + Evidence Inventory.

### Exit gate
The team can say what evidence exists, where it came from and what perspective it represents.

---

## Phase 1 — Atomic Evidence Extraction

### Goal
Extract claims before generating requirements or features.

Each important claim receives:
- claim ID;
- normalized statement;
- source ID;
- exact locator/citation when possible;
- source perspective;
- epistemic status;
- confidence/limitations.

### Status model

- **FACT** — directly supported by evidence, limited to what that evidence actually proves.
- **INFERENCE** — interpretation derived from one or more facts.
- **ASSUMPTION** — plausible but insufficiently supported.
- **OPEN QUESTION** — materially unknown.
- **DECISION** — explicit choice made by the POC team.

### Critical rule
> A stakeholder saying that users need something is a fact about the stakeholder statement; it is not automatically a fact about user behavior or need.

### Output
Research Board + Claim Ledger.

### Exit gate
No high-impact downstream statement needs to rely on hidden reasoning.

---

## Phase 2 — CSD / Research Synthesis

### Goal
Create a shared epistemic map of the project.

Translate the evidence into:

```text
CERTAINTIES  → evidence-backed facts
SUPPOSITIONS → inferences / assumptions
DOUBTS       → open questions
```

Track risks created by unresolved suppositions/doubts.

### Rule
> No assumption may become a fact because it appears repeatedly in agent-generated documents.

### Output
`RESEARCH-BOARD.md`.

### Exit gate
The problem can be explained without proposing screens.

---

## Phase 3 — Actors and Stakeholders

### Goal
Understand who participates in the system and whose work the POC is attempting to support.

Distinguish:
- client/stakeholder;
- primary functional actor;
- secondary actor;
- operator;
- administrator;
- support/implementation actor;
- external organization/system.

### No-client rule
When direct user evidence is unavailable, prefer **functional actors** to fictional personas.

Do not invent demographics, motivations, emotions or quotes.

### Output
Actor Map + Stakeholder Map.

### Exit gate
There is a defensible primary actor for the POC and the evidence level behind that choice is explicit.

---

## Phase 4 — Domain + Operational Model

### Goal
Understand the system as concepts, relationships, events and work before turning it into navigation.

Identify:
- glossary/terminology;
- entities;
- relationships;
- events;
- states/lifecycles;
- business rules;
- ownership;
- data sources;
- external IDs;
- sensitive data;
- external systems/interfaces;
- optional vs required relationships.

Useful questions:
- What exists independently?
- What produces events?
- What changes state?
- What belongs to what?
- Which actor performs which task?
- Which data is optional?
- Which behavior is only inferred?

### Output
Domain Model v0.x + glossary.

### Exit gate
The core scenario can be modeled without page names.

---

## Phase 5 — Current-State / Concept of Operations

### Goal
Reconstruct how the relevant outcome is achieved today and how the surrounding operation works.

Capture:
- trigger;
- actor;
- goal;
- preconditions;
- actions;
- systems/touchpoints;
- information exchanged;
- decisions;
- delays;
- handoffs;
- workarounds;
- exceptions;
- consequence;
- source evidence.

If current behavior is not actually observed, label the map **source-derived** or **hypothetical**, not user-validated.

### Output
Current-State Journey / Operational Scenario.

### Exit gate
The primary friction is stated as a workflow/problem condition, not merely a requested feature.

---

## Phase 6 — Service Blueprint (Conditional)

Use when the POC depends on multiple devices, channels, teams, integrations or backstage processes.

### Layers
1. Actor/customer actions.
2. Frontstage touchpoints.
3. Backstage systems/processes.
4. Support processes/dependencies.

### Purpose
Prevent UI from hiding integration, operational or organizational problems.

### Output
Service Blueprint v0.x.

### Exit gate
Critical backstage dependencies and failure points are visible.

---

## Phase 7 — Evidence Challenge and Triangulation

### Goal
Reduce uncertainty before requirements become design commitments.

There are two modes.

### Mode A — Direct research available
Use interviews, contextual research, usability testing, analytics/support data or other appropriate methods.

### Mode B — Evidence-constrained POC (default when no client/user access)
Use only the strongest available substitutes:
- official technical documentation;
- regulations/standards;
- provided analytics/support material;
- secondary/domain research;
- competitor/reference analysis;
- technical feasibility review;
- expert review;
- heuristic evaluation;
- cognitive/task walkthrough;
- scenario inspection.

### Rule
These activities can **triangulate, verify, challenge or reduce uncertainty**. They do not become direct user validation.

### Output
Updated Research Board with evidence status and unresolved-risk list.

### Exit gate
The team knows which uncertainties can be safely carried into the POC and which would invalidate the vertical slice.

---

## Phase 8 — Requirements Engineering

### Goal
Transform accepted evidence into traceable, atomic and verifiable requirements.

Use:
- `EVIDENCE-TO-REQUIREMENTS.md`;
- `templates/REQUIREMENTS-LEDGER.md`;
- `EVALS.md`.

Classify every candidate as:
- **EXPLICIT REQUIREMENT**;
- **DERIVED REQUIREMENT**;
- **PROVISIONAL REQUIREMENT**;
- **DESIGN HYPOTHESIS**;
- **REFERENCE PATTERN**.

### Requirement baseline rule
Every accepted P0 requirement must:
- trace to a source/claim or explicit derivation;
- contain one obligation;
- use project terminology;
- have rationale;
- expose assumption dependencies;
- define an observable fit criterion;
- define a verification method.

### Traceability chain

```text
SOURCE → CLAIM → REQUIREMENT → DECISION → FLOW/UI → TEST
```

### Exit gate
A skeptic agent cannot find an unsupported P0 requirement masquerading as fact.

---

## Phase 9 — POC Definition

### Goal
Choose the smallest vertical slice that tests the most important product/design/technical uncertainty.

Use `templates/POC-BRIEF.md`.

Define:
- problem statement;
- primary actor;
- hypothesis;
- learning goal;
- scenario;
- in scope;
- out of scope;
- success evidence;
- known mocks/stubs;
- what must be real;
- requirements included in the slice;
- unresolved assumptions carried into the slice.

### POC rule
> Scope is determined by the question the POC must answer.

Not by generic SaaS completeness or stakeholder wishlist size.

### Exit gate
A reviewer can explain what the POC proves, what it does not prove and what would be learned if it fails.

---

## Phase 10 — Future-State Hypothesis

### Goal
Describe the smallest improved end-to-end journey worth exploring.

This is explicitly a hypothesis until evidence supports it.

Structure:
- trigger;
- actor intent;
- system response;
- information needed;
- decisions;
- exceptions;
- desired outcome;
- linked requirements;
- unresolved assumptions.

### Rule
Do not add features because they are common in SaaS/admin products.

### Output
Future-State Journey v0.x.

### Exit gate
The journey is coherent and traceable to the POC learning goal.

---

## Phase 11 — Information Architecture

### Goal
Organize information around tasks, domain concepts and accepted requirements.

Avoid generic navigation such as `Dashboard / Users / Reports / Settings` unless evidence or an explicit design hypothesis justifies it.

### Output
IA v0.x with rationale and upstream references.

### Exit gate
Every top-level area supports a known task/domain concept or explicitly labeled hypothesis.

---

## Phase 12 — Critical Task Flows

### Goal
Define 1–3 flows that exercise the POC hypothesis.

Each flow states:
- entry condition;
- actor goal;
- required information;
- decisions;
- happy path;
- meaningful empty/loading/error/exception states;
- completion condition;
- requirement IDs exercised.

### Output
Task Flows.

### Exit gate
The POC can be evaluated as tasks, not merely browsed as screens.

---

## Phase 13 — Prototype

### Goal
Create the minimum interface fidelity required to inspect/test the hypothesis.

Principles:
- realistic content/data;
- critical states included;
- no polish outside the hypothesis without reason;
- uncertainty remains annotated;
- use a component/system foundation where possible;
- target viewport reflects supplied evidence or is labeled a design assumption.

### Output
Testable prototype.

### Exit gate
A reviewer can execute the critical flows without hidden explanation.

---

## Phase 14 — Front-End POC

### Goal
Turn the interaction model into a credible executable vertical slice.

Front-end is part of validation/verification work, not merely handoff.

Requirements:
- preserve accepted task flows;
- use realistic states/data;
- mark mocks clearly;
- never fake real-time/backend capability;
- basic keyboard/accessibility works;
- implementation does not silently change product decisions;
- code outside the POC learning goal remains proportional.

Before coding, agents must read:
1. Research Board;
2. Requirements Ledger;
3. POC Brief;
4. Domain Model;
5. critical flows;
6. technical constraints.

### Exit gate
The vertical slice is stable enough for inspection or representative testing if access later becomes available.

---

## Phase 15 — Verification and Evaluation

### Goal
Determine what the POC actually demonstrates.

### Verification
Ask: **Did we build the specified POC correctly?**

Methods may include:
- test;
- demonstration;
- inspection;
- analysis;
- accessibility review;
- technical checks;
- requirement traceability review.

### Validation
Ask: **Is this the right product/experience for the intended user and context?**

If representative users are unavailable, this remains **not user-validated**.

### Evidence-constrained evaluation
Use:
- scenario walkthrough;
- cognitive/task walkthrough;
- heuristic inspection;
- multi-reviewer design review;
- technical/domain review;
- competitive/reference comparison;
- requirements verification matrix.

### Output
Findings + Verification Matrix + explicit validation status.

### Exit gate
No claim about the POC exceeds the evidence produced by the evaluation.

---

## Phase 16 — Decision

Options:
- **Proceed** — evidence supports expanding the next slice.
- **Iterate** — core direction remains plausible but needs correction.
- **Pivot** — evidence changes the problem/model/solution direction.
- **Stop** — not valuable or feasible enough.

Record:
- what was learned;
- what was verified;
- what remains unvalidated;
- what changed;
- what remains unknown;
- next recommendation;
- obsolete/superseded artifacts.

---

## Phase 17 — Compound the Learning

A POC should make the next POC easier and more reliable.

After each real project:
1. identify reusable failures/successes in extraction;
2. identify repeated agent hallucination patterns;
3. add useful examples to `EVALS.md`/eval cases;
4. improve templates/gates only when reusable;
5. distinguish project knowledge from process knowledge;
6. update `CHANGELOG.md`.

```text
REAL POC FAILURE / LEARNING
       ↓
IS IT REUSABLE?
   ├── NO → project artifact only
   └── YES
        ↓
PROCESS / TEMPLATE / AGENT RULE
        ↓
EVAL CASE
        ↓
FUTURE REGRESSION CHECK
```

---

# Recommended agent architecture

Default to an orchestrated workflow, not an autonomous swarm:

```text
Corpus Analyst
   ↓
Evidence Extractor
   ↓
Domain Modeler
   ↓
Requirements Engineer
   ↓
Skeptic / Red Team
   ↓
Reviser
   ↓
Quality Judge
   ↓
UX / Product Modeler
   ↓
Builder
```

Use parallel source analysis only when the corpus is large. Truth is determined by evidence, not agent vote.

---

# Minimum artifact set per POC

```text
projects/<project>/
  README.md
  SOURCE-MANIFEST.md
  RESEARCH-BOARD.md
  REQUIREMENTS-LEDGER.md
  POC-BRIEF.md
  DOMAIN-MODEL.md
  CURRENT-JOURNEY.md
  SERVICE-BLUEPRINT.md        # conditional
  FUTURE-JOURNEY.md
  IA.md
  TASK-FLOWS.md
  VERIFICATION-MATRIX.md
  FINDINGS.md
  DECISION.md
```

The project may use fewer files if the same information remains explicit, traceable and agent-readable.

# Methodological foundations

The process draws selectively from established disciplines rather than copying one framework wholesale:

- Requirements Engineering: ISO/IEC/IEEE 29148.
- Requirements quality, V&V and traceability: NASA Systems Engineering guidance / INCOSE principles.
- Atomic requirements, rationale, fit criteria and work-vs-product scope: Volere.
- Requirements lifecycle/traceability: IREB.
- UX discovery, CSD, task analysis, journey mapping, service blueprinting and inspection methods: Nielsen Norman Group.
- Agent orchestration and evaluator/optimizer patterns: current agent-engineering guidance from leading model providers.

External methodology supports process quality. It never overrides project evidence.