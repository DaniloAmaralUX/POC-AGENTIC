# Requirements Ledger Template

**Project:**  
**Version:**  
**Date:**  
**Status:** draft | baseline | superseded

This ledger is the canonical bridge between source evidence and design/build work.

## Requirement taxonomy

- BUSINESS
- USER / TASK
- FUNCTIONAL
- DATA
- BUSINESS RULE
- INTEGRATION
- CONSTRAINT
- NON-FUNCTIONAL
- LEGAL / PRIVACY
- OBSERVABILITY / OPERATIONS

## Origin taxonomy

- EXPLICIT — directly requested or mandated by project evidence.
- DERIVED — necessary consequence of accepted evidence/constraints.
- PROVISIONAL — useful for the POC but depends on unresolved assumptions.
- DESIGN HYPOTHESIS — proposed solution, not a requirement.
- REFERENCE PATTERN — external pattern/reference, not a requirement by itself.

---

## Ledger

| ID | Type | Origin | Requirement / Hypothesis | Rationale | Source / Claim | Assumption Dependencies | Priority | Fit Criterion | Verification | Status |
|---|---|---|---|---|---|---|---|---|---|---|
| REQ-F-001 | FUNCTIONAL | EXPLICIT |  |  | S- / C- | — | P0 |  | demonstration | proposed |

---

## Atomic requirement card

Use this block when a requirement needs more context than the table can hold.

```yaml
id: REQ-F-001
type: functional
status: proposed
origin: explicit
statement: "The system shall ..."
rationale: ""
sources:
  - claim: C-001
    source: S-001
    locator: ""
assumption_dependencies: []
priority: P0
fit_criterion: ""
verification: demonstration
scope: POC
owner: ""
notes: ""
```

---

## Quality gateway

Before a requirement is accepted into the POC baseline, verify:

- [ ] Source grounding exists.
- [ ] Source actually entails the statement.
- [ ] Epistemic level is correct.
- [ ] One obligation only.
- [ ] Terminology matches project glossary.
- [ ] Rationale exists.
- [ ] No unresolved contradiction is hidden.
- [ ] No unsupported technical capability is assumed.
- [ ] Fit criterion is observable.
- [ ] Verification method is defined.
- [ ] Scope is explicit.

If any item fails, revise or downgrade the item to PROVISIONAL / ASSUMPTION / OPEN QUESTION / DESIGN HYPOTHESIS.

---

## Orphan checks

### Orphaned evidence
Important claims with no requirement, rule, decision or explicit reason for exclusion.

| Claim | Why important | Downstream destination / exclusion rationale |
|---|---|---|
| C- |  |  |

### Orphaned requirements
Requirements with no source or valid derivation.

| Requirement | Problem | Resolution |
|---|---|---|
| REQ- |  | downgrade / remove / find evidence |

### Orphaned design
Screens, features or states with no upstream requirement/hypothesis.

| UI / Flow | Upstream rationale missing | Resolution |
|---|---|---|
| UI- |  |  |

---

## Baseline rule

A P0 requirement may be provisional when the POC explicitly exists to test that uncertainty, but it must never masquerade as confirmed fact.