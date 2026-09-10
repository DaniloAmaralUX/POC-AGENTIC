# AGENTS.md — Operating Contract

This repository is designed to be read by AI agents and humans. Any agent working on a POC that uses this process must follow this contract.

## Start here

Before acting:

1. Read `README.md`.
2. Read `PROCESS.md`.
3. Read `EVIDENCE-TO-REQUIREMENTS.md`.
4. Read `EVALS.md`.
5. Read `GATES.md`.
6. Locate the target project folder.
7. Read its source manifest, research board, requirements ledger and POC brief before proposing IA, UI or code.

If required upstream artifacts do not exist, create the missing synthesis before continuing downstream.

---

## Default operating constraint

Assume that direct client/end-user access may not exist.

When that is true:
- do not fabricate interviews, quotes, personas or observed behavior;
- do not call stakeholder-derived beliefs user facts;
- do not call desk research or expert inspection user validation;
- explicitly label what is source-grounded, inferred, provisional, technically verified, expert-reviewed or not user-validated.

A polished POC is not evidence of user validity.

---

## Evidence discipline

Every important statement must be classified as one of:

- **FACT** — directly supported by source evidence, limited to what the source actually proves.
- **INFERENCE** — interpretation derived from one or more facts.
- **ASSUMPTION** — plausible but not sufficiently supported.
- **OPEN QUESTION** — materially unknown.
- **DECISION** — an explicit product/design/technical choice.

Every candidate requirement must additionally be classified as:

- **EXPLICIT**;
- **DERIVED**;
- **PROVISIONAL**;
- **DESIGN HYPOTHESIS**;
- **REFERENCE PATTERN**.

### Never do this

- stakeholder opinion → user fact;
- competitor feature → requirement;
- common SaaS pattern → requirement;
- agent inference → technical fact;
- repeated assumption → certainty;
- source mention → unsupported stronger claim;
- mocked behavior → real capability.

---

## Required provenance chain

For important P0 scope, preserve:

```text
SOURCE → CLAIM → REQUIREMENT → DECISION → FLOW/UI → VERIFICATION
```

A citation alone is insufficient if the source does not entail the downstream statement.

---

## Agent workflow

Default sequence:

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

Do not collapse extraction, interpretation, criticism and final synthesis into one unchecked pass when the corpus is ambiguous.

### Corpus Analyst
Read the full available corpus, create source IDs and expose missing/contradictory material.

### Evidence Extractor
Extract atomic claims with locators. Do not propose UI.

### Domain Modeler
Extract vocabulary, actors, entities, events, states, business rules, data and external-system boundaries.

### Requirements Engineer
Transform evidence into atomic requirements using `templates/REQUIREMENTS-LEDGER.md`.

### Skeptic / Red Team
Try to disprove requirements. Look for hallucination, source overreach, contradictions, solution creep, hidden assumptions and invented capabilities.

### Reviser
Make the smallest correction or downgrade the epistemic status.

### Quality Judge
Run `EVALS.md` and `GATES.md`. Evidence, not agent consensus, determines truth status.

### UX / Product Modeler
Only after requirements quality gates, derive POC scope, future-state hypotheses, IA and critical task flows.

### Builder
Implement the accepted vertical slice without silently changing upstream product decisions.

---

## Parallelism

Parallelize reading when the corpus is large. Do not parallelize truth by majority vote.

Multiple agents may independently inspect a high-risk section, but disagreement must be resolved against source evidence or left unresolved.

---

## External research

External sources may:
- explain domain terminology;
- identify standards/regulations;
- challenge assumptions;
- provide competitor/reference patterns;
- support technical feasibility review;
- provide established UX/process guidance.

They must not silently overwrite the project corpus.

Classify external material as authoritative constraint, domain reference, competitive reference, design pattern or process reference.

---

## Product / UX rules

Do:
- design around critical tasks and source-grounded domain concepts;
- keep future-state work explicitly hypothetical where evidence is weak;
- include meaningful empty/loading/error/exception states;
- preserve uncertainty in annotations;
- separate functional actor from invented persona.

Do not:
- default to `Dashboard / Users / Reports / Settings`;
- add features merely to make the POC look complete;
- infer emotions/motivations without evidence;
- use external patterns as proof of user need.

---

## Front-end rules

Do:
- preserve approved task flows;
- use realistic content/data;
- mark stubs/mocks clearly;
- maintain basic accessibility and keyboard operation;
- keep abstractions proportional to real reuse;
- preserve requirement IDs where practical in implementation/test notes.

Do not:
- fabricate backend states;
- fake real-time behavior;
- rewrite product logic because implementation is easier;
- over-engineer outside the learning goal.

---

## Verification vs validation

Verification asks whether the POC satisfies its specified requirements.

Validation asks whether it is the right product/experience for intended users/context.

If representative users were not involved, the agent must explicitly state **not user-validated**.

Permitted evidence-constrained evaluation includes scenario walkthrough, cognitive/task walkthrough, heuristic inspection, design review, technical review and requirements traceability review.

---

## Gate discipline

Before moving phases, check `GATES.md`.

If a gate fails:
- state why;
- identify the smallest missing evidence/decision;
- stop the affected path or continue only as explicitly provisional.

---

## Updating the canonical process

Update the process only when a real POC exposes a reusable process failure/improvement.

When changing it:
1. record the observed failure;
2. define the reusable rule;
3. update `PROCESS.md` and affected templates;
4. update this contract if agent behavior changes;
5. add/adjust an eval case where useful;
6. update `CHANGELOG.md`.

Ask:
> Would this improve multiple future POCs, or is it project-specific?

Only the first belongs in the canonical method.

---

## Handoff standard

Another agent should be able to recover without hidden reasoning:
- what sources exist;
- what each source can and cannot prove;
- what is fact/inference/assumption/question;
- what the domain model is;
- what requirements are explicit/derived/provisional;
- what the POC hypothesis is;
- what is in/out of scope;
- what is mocked vs real;
- what is verified vs unvalidated;
- which gate is current;
- what should happen next.

If those answers are not recoverable from the repository, the handoff is incomplete.