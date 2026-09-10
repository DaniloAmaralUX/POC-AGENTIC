# Agentic POC Evals

**Purpose:** make the POC process measurable and regressible as agents, prompts and templates evolve.

The process is not considered improved because an agent writes more polished documents. It improves when it produces fewer unsupported requirements, preserves more source truth and yields clearer, testable product decisions.

## Core eval dimensions

### 1. Grounding
Question: does each accepted requirement have source support?

Hard rule:
- every P0 requirement must trace to at least one claim/source;
- if not, it is provisional, assumption or design hypothesis.

Failure example:
> "The system must have role-based access control"

when no source or derived constraint establishes roles.

---

### 2. Entailment
Question: does the cited evidence actually support the requirement, rather than merely mention the topic?

A citation is not proof if the transformation changes meaning.

Evaluator task:
- inspect requirement;
- inspect source excerpt;
- classify `supported / partially-supported / unsupported / contradictory`;
- explain the minimum correction.

---

### 3. Coverage
Question: did the extraction miss important source needs, constraints, actors, exceptions or business rules?

Method:
1. identify high-salience source claims independently;
2. compare them against the canonical claim/requirements ledger;
3. flag orphaned high-salience claims.

Do not optimize for extracting every sentence. Optimize for relevant coverage.

---

### 4. Epistemic honesty
Question: are facts, inferences, assumptions, questions and decisions correctly separated?

Critical failure:
- stakeholder belief → user fact;
- competitor pattern → product requirement;
- model inference → technical capability;
- repeated assumption → "certainty".

---

### 5. Atomicity
Question: does each requirement express one obligation?

Bad:
> The portal shall show equipment status, send alerts and allow admins to export reports.

Better:
- one requirement for status visibility;
- one for alerts;
- one for export, if each is supported.

---

### 6. Ambiguity
Flag terms such as:
- intuitive;
- fast;
- modern;
- easy;
- real time;
- robust;
- seamless;
- complete;

unless a project-defined meaning or fit criterion exists.

---

### 7. Contradiction detection
Search for conflicts across:
- sources;
- requirements;
- business rules;
- actor permissions;
- states;
- technical constraints;
- POC scope.

Do not resolve conflict by preference. Record it.

---

### 8. Verifiability
Question: can the POC inspect, demonstrate, analyze or test whether the requirement is satisfied?

Every P0 requirement should have a verification method and observable fit criterion appropriate to POC fidelity.

---

### 9. Scope discipline
Question: did generic SaaS conventions enter without evidence?

Common hallucinated additions:
- dashboards;
- team management;
- settings;
- roles;
- notifications;
- exports;
- billing;
- audit logs;
- AI assistant;
- onboarding wizard.

These may be excellent design hypotheses. They are not requirements merely because they are common.

---

### 10. Traceability completeness
Expected chain:

```text
source → claim → requirement → decision → flow/state → verification
```

Flag:
- requirement with no source/derivation;
- UI surface with no requirement/decision;
- requirement with no verification path;
- test with no requirement/hypothesis.

---

## Agent evaluator pattern

Recommended loop:

```text
DRAFT
  ↓
CRITIC
  ↓
REVISE
  ↓
JUDGE
  ↓
PASS / FAIL / PROVISIONAL
```

The critic must not rewrite the artifact first. It should identify defects with evidence.

The reviser then makes the smallest correction.

The judge checks the revised artifact against the same rubric.

---

## Eval case library

Create reusable cases from real POCs:

```text
evals/cases/<case-id>/
  source.md
  expected-claims.md
  expected-failures.md
  notes.md
```

Good cases are not necessarily complete POCs. A short transcript section that previously caused a hallucinated requirement is valuable.

Recommended case categories:
- stakeholder opinion mistaken for user fact;
- ambiguous pronoun/entity;
- contradictory sources;
- technical capability not established;
- optional relationship made mandatory;
- external reference promoted to requirement;
- nonfunctional adjective without fit criterion;
- multi-obligation requirement;
- privacy-sensitive field added by convention;
- current-state pain turned directly into requested feature.

---

## Process regression rule

When `PROCESS.md`, prompts, agent roles or templates change:

1. run representative eval cases;
2. compare new vs previous failures;
3. reject changes that improve prose but reduce grounding/traceability;
4. record meaningful process changes in `CHANGELOG.md`.

## Success principle

The goal is not zero inference.

The goal is **controlled inference with visible provenance and uncertainty**.