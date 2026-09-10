# Evidence-to-Requirements Pipeline

**Status:** canonical supporting method  
**Applies to:** POCs where the team receives briefs, transcripts, PDFs, screenshots, technical docs or stakeholder material but has no direct access to the client or end users.

## Why this exists

In this operating mode, the main risk is not lack of output. It is false certainty.

An agent can read ambiguous material and quickly produce a polished PRD, IA and UI. That speed is dangerous if source statements, inferences and generic product patterns are silently converted into requirements.

The pipeline therefore treats requirements extraction as an **evidence transformation problem**.

```text
SOURCE
  ↓
CLAIM
  ↓
CLASSIFICATION
  ↓
DOMAIN / RULE
  ↓
REQUIREMENT
  ↓
DESIGN DECISION
  ↓
IMPLEMENTATION
  ↓
VERIFICATION
```

Every downstream artifact must be traceable upstream.

---

## 1. Source Manifest

Before synthesis, assign IDs to every input.

Example:

```text
S-001  Meeting transcript · 2026-09-08 · stakeholder
S-002  Product manual · Centurion · technical
S-003  Screenshot set · existing portal · reference
S-004  LGPD guidance · official/legal
```

For each source record:
- title;
- date/version when known;
- source type;
- perspective;
- authority/reliability notes;
- scope;
- known limitations.

A stakeholder transcript is strong evidence that the stakeholder **said** something. It is not automatically evidence that an end user behaves that way.

---

## 2. Atomic Claim Ledger

Extract claims before writing requirements.

Each claim receives an ID and provenance.

```yaml
id: C-014
statement: "The client wants equipment data available remotely."
source: S-001
locator: "p.24 / timestamp 30:27–31:23"
perspective: stakeholder
status: fact-about-source
confidence: high
```

Allowed epistemic states:

- **FACT** — directly supported by evidence, scoped to what the evidence actually proves.
- **INFERENCE** — interpretation derived from one or more facts.
- **ASSUMPTION** — plausible but unsupported or insufficiently supported.
- **OPEN QUESTION** — materially unknown.
- **DECISION** — explicit product/design/technical choice made by the POC team.

Important: a repeated agent inference is still an inference.

---

## 3. CSD Translation

Use the CSD logic as a synthesis layer:

```text
CERTAINTIES   → FACTS with evidence
SUPPOSITIONS  → INFERENCES / ASSUMPTIONS
DOUBTS        → OPEN QUESTIONS
```

Do not attempt to move every doubt to certainty when direct research is impossible. Instead, expose the unresolved risk and decide whether the POC can safely proceed with it as provisional.

---

## 4. Terminology and Domain Extraction

Before feature extraction, build:

- glossary;
- actors;
- entities;
- relationships;
- events;
- states;
- business rules;
- constraints;
- external systems;
- sensitive data;
- integration boundaries.

Prefer the vocabulary used by the source material. If two sources use different words for the same concept, record the conflict before normalizing terminology.

Useful model:

```text
ACTOR → performs → TASK
ENTITY → produces → EVENT
EVENT → changes → STATE
RULE → constrains → ACTION
SYSTEM → exchanges → DATA
```

---

## 5. Operational Concept / Scenario

Before page names, reconstruct how the work happens.

For each critical scenario describe:

1. trigger;
2. actor;
3. goal;
4. preconditions;
5. current actions;
6. systems/touchpoints;
7. information exchanged;
8. decision points;
9. failure/exception cases;
10. desired outcome.

If the behavior is inferred rather than observed, label the scenario **hypothetical**.

---

## 6. Requirement Transformation

Requirements are created only after claims, domain concepts and constraints exist.

Classify each candidate requirement as:

- **EXPLICIT** — directly requested or mandated by project evidence;
- **DERIVED** — necessary consequence of accepted facts/constraints;
- **PROVISIONAL** — useful for the POC but depends on unresolved assumptions;
- **DESIGN HYPOTHESIS** — proposed solution, not a requirement;
- **REFERENCE PATTERN** — learned from external research/competitors; never a requirement by itself.

Do not collapse these categories.

---

## 7. Atomic Requirement Shell

Each accepted candidate requirement should be representable as:

```yaml
id: REQ-F-012
type: functional
status: proposed
origin: explicit | derived | provisional
statement: "The system shall ..."
rationale: "Why this exists"
sources:
  - claim: C-014
    source: S-001
assumption_dependencies: []
priority: P0 | P1 | P2
fit_criterion: "Observable condition that shows this requirement is met"
verification: test | demonstration | inspection | analysis
scope: POC | later
notes: ""
```

Rules:
- one requirement, one obligation;
- use consistent terminology;
- avoid vague adjectives without a fit criterion;
- every accepted P0 requirement must have provenance;
- derived requirements must state the derivation rationale;
- if the source cannot support the statement, downgrade it to an assumption or design hypothesis.

---

## 8. Requirement Types

Minimum useful taxonomy:

```text
BUSINESS
USER / TASK
FUNCTIONAL
DATA
BUSINESS RULE
INTEGRATION
CONSTRAINT
NON-FUNCTIONAL
LEGAL / PRIVACY
OBSERVABILITY / OPERATIONS
```

A single source statement may generate multiple atomic requirements of different types, but each transformation must be explicit.

---

## 9. Requirement Quality Gateway

A requirement cannot enter the POC baseline until a verifier checks:

### Grounding
Does the cited source actually support it?

### Scope
Is the claim about business, user, technology or solution being represented at the correct level?

### Atomicity
Does it contain one obligation?

### Clarity
Can two agents interpret it the same way?

### Necessity
Is there a rationale for including it?

### Consistency
Does it conflict with another accepted requirement?

### Feasibility awareness
Does it assume a technical capability not established by evidence?

### Verifiability
Can the POC show whether it is satisfied?

### Traceability
Can it be traced to source/claim and later to design/test?

Failure does not mean delete. It may mean downgrade to provisional, assumption or open question.

---

## 10. Agent Workflow

Default to a controlled workflow, not a free-form swarm.

```text
CORPUS ANALYST
      ↓
EVIDENCE EXTRACTOR
      ↓
DOMAIN MODELER
      ↓
REQUIREMENTS ENGINEER
      ↓
SKEPTIC / RED TEAM
      ↓
REVISER
      ↓
QUALITY JUDGE
      ↓
UX / PRODUCT MODELER
      ↓
BUILDER
```

### Corpus Analyst
Reads the entire corpus, creates the source manifest and identifies missing/garbled material.

### Evidence Extractor
Produces atomic claims with source locators. It does not propose features.

### Domain Modeler
Extracts vocabulary, actors, entities, rules, events, states and boundaries.

### Requirements Engineer
Transforms evidence into explicit/derived/provisional requirements using the requirement shell.

### Skeptic / Red Team
Attempts to disprove each requirement. Searches for unsupported leaps, contradictions, solution creep and invented capabilities.

### Reviser
Corrects or downgrades findings from the critic.

### Quality Judge
Runs the requirements quality gateway and coverage/traceability checks.

### UX / Product Modeler
Only after the gate, derives POC scope, future-state hypotheses, IA and task flows.

### Builder
Implements only the accepted/provisional scope and preserves traceability.

---

## 11. Parallelism Rules

Parallelize **evidence reading**, not truth.

For large corpora, multiple source analyzers may work independently, but their claims must converge into one canonical ledger.

Use independent reviewers for high-risk sections. Do not let multiple agents vote an unsupported claim into a fact.

The final epistemic status is determined by evidence, not majority vote.

---

## 12. External Research

External research can improve interpretation but has strict roles.

Allowed uses:
- understand domain terminology;
- identify regulatory/technical constraints;
- inspect comparable workflows;
- discover established interaction patterns;
- challenge assumptions;
- generate questions;
- find standards and authoritative references.

External research must not silently overwrite the project corpus.

Classify it as:

```text
AUTHORITATIVE CONSTRAINT
DOMAIN REFERENCE
COMPETITIVE REFERENCE
DESIGN PATTERN
PROCESS REFERENCE
```

A competitor having a feature is not evidence that this POC needs the feature.

---

## 13. Traceability Graph

The desired chain is:

```text
S-001 Source
  ↓
C-014 Claim
  ↓
REQ-F-012 Requirement
  ↓
DEC-006 Design decision
  ↓
FLOW-002 Critical task flow
  ↓
UI-004 Screen/state
  ↓
TEST-009 Verification task
```

Every important UI surface should be explainable through this chain.

---

## 14. No-Client / No-User Validation Rule

When direct access is unavailable, do not call the result "user validated".

Use these statuses instead:

- **source-grounded**;
- **triangulated**;
- **expert-reviewed**;
- **technically verified**;
- **prototype-inspected**;
- **provisional**;
- **not validated with users**.

Substitute activities may include:
- official technical documentation;
- regulations/standards;
- existing analytics/support material when provided;
- competitive/reference analysis;
- heuristic evaluation;
- cognitive/task walkthrough;
- scenario inspection;
- design review;
- technical feasibility review.

These reduce uncertainty. They do not become direct user evidence.

---

## 15. POC Entry Rule

The POC may proceed without direct user validation only if:

1. the core problem is source-grounded enough to justify exploration;
2. all P0 requirements have traceability;
3. unresolved assumptions are visible;
4. critical technical unknowns are mocked or explicitly deferred;
5. the POC is framed as a learning artifact, not proof of market/user validation;
6. success criteria distinguish verification from validation.

---

## 16. Continuous Improvement

After every POC, inspect failures in this pipeline.

Examples:
- source statement lost during extraction;
- inferred user need promoted to requirement;
- requirement too vague to test;
- hidden contradiction discovered during build;
- screen added with no upstream rationale;
- technical capability invented by UI;
- agent repeatedly misclassifies a domain term.

If the failure is reusable across projects:

```text
REAL FAILURE CASE
   ↓
ADD TO PROCESS / TEMPLATE
   ↓
ADD TO EVAL CASESET
   ↓
RE-RUN AGAINST FUTURE CHANGES
```

The process should become stricter where real POCs prove agents are unreliable and simpler where gates add no learning value.