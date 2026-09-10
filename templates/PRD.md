# POC PRD — <PROJECT>

**Version:** 0.1  
**Status:** Draft | Baseline | Superseded  
**Date:** YYYY-MM-DD  
**Owner:**  
**Current Gate:**

> This PRD is the delivery contract between evidence, product/UX design and front-end implementation. It must not create certainty that does not exist upstream.

---

## 1. Executive Summary

### Product / POC
<One-paragraph description.>

### Why this POC exists
<Problem/opportunity in workflow terms, not a feature request.>

### Primary actor
<Role + context.>

### Primary hypothesis
> If we <intervention>, then <actor> can <outcome>, because <evidence-backed reason>.

### Primary learning goal
> At the end of this POC we need to know whether...

---

## 2. Evidence Basis

### Project sources
| Source ID | Source | Perspective | Date/version | Reliability / limitation |
|---|---|---|---|---|
| S-001 |  | stakeholder / technical / legal / user / other |  |  |

### Evidence status
- FACTS:
- INFERENCES:
- ASSUMPTIONS:
- OPEN QUESTIONS:

Link to canonical Research Board: `<path>`

---

## 3. Problem Definition

### Current-state problem
<What is difficult, slow, risky or impossible today?>

### Current-state journey
<Short synthesis + link to CURRENT-JOURNEY.md>

### Primary friction
> <One sentence.>

### Consequence
<User/business/operational consequence.>

---

## 4. Product Boundary

### In scope
Only what is necessary to make the POC hypothesis credible and testable.

- 

### Out of scope
- 

### External systems / boundaries
| System / actor | Relationship | In our control? | Real / mocked in POC |
|---|---|---:|---|
|  |  |  |  |

---

## 5. Actors and Permissions

| Actor | Goal | Key tasks | Evidence level | Included in POC? |
|---|---|---|---|---:|
| Primary actor |  |  | fact / inferred / provisional | yes |

Do not invent demographic personas without evidence.

---

## 6. Domain Model

Link: `<DOMAIN-MODEL.md>`

### Core entities
| Entity | Definition | Key relationships | Optional / required notes |
|---|---|---|---|
|  |  |  |  |

### Critical states
- 

### Sensitive / regulated data
- 

---

## 7. Requirements Baseline

Canonical source: `<REQUIREMENTS-LEDGER.md>`

Only accepted P0/P1 requirements belong here. Do not duplicate the entire ledger.

| ID | Requirement | Origin | Priority | Fit criterion | Verification |
|---|---|---|---|---|---|
| REQ- |  | explicit / derived / provisional | P0 |  | inspection / demonstration / test / analysis |

### Design hypotheses
These are proposed solutions, not requirements.

| ID | Hypothesis | Upstream rationale | What would falsify it? |
|---|---|---|---|
| DH-001 |  |  |  |

---

## 8. Critical User Journeys

Limit POC scope to 1–3 journeys.

### Journey 1 — <name>
- Trigger:
- User intent:
- Entry condition:
- Key decisions:
- Success condition:
- Important exceptions:

### Journey 2 — <name>
- 

Link to detailed task flows: `<TASK-FLOWS.md>`

---

## 9. Information Architecture

Link: `<IA.md>`

### Top-level areas
| Area | User task / domain rationale | Requirement / hypothesis supported |
|---|---|---|
|  |  |  |

Rule: no generic SaaS area exists without a task/domain rationale.

---

## 10. Experience Requirements

### Content and terminology
- Use project glossary.
- Avoid invented language when source terminology exists.

### Required interface states
For critical flows only:
- default;
- loading;
- empty;
- success;
- error;
- attention/exception;
- permission, where relevant.

### Accessibility
- Keyboard operation for critical flows.
- Visible focus.
- Semantic labels.
- Information not communicated by color alone.
- Appropriate contrast.

### Responsive target
<Desktop / tablet / mobile and why.>

---

## 11. Design Delivery Contract

Canonical design specification: `<DESIGN-SPEC.md>`

Design must deliver:
- critical task flows;
- IA reflected in navigation;
- realistic content/data;
- key states;
- interaction rules;
- component/pattern decisions;
- responsive behavior for target context;
- accessibility behavior;
- annotations for provisional/mock behavior;
- evidence traceability for major decisions.

Design is ready for build only when `Gate F — Flow Ready` and the Design Readiness checklist pass.

---

## 12. Front-End Delivery Contract

Canonical implementation specification: `<FRONTEND-SPEC.md>`

Front-end must deliver:
- executable vertical slice of approved critical flows;
- realistic fixture/mock data;
- explicit mocked integrations;
- state coverage required by the POC;
- basic keyboard/accessibility behavior;
- target responsive behavior;
- stable routes/navigation where relevant;
- no fabricated backend capability;
- implementation traceable to requirements/design decisions.

Front-end is not required to build production backend, authentication, billing or integrations unless the POC hypothesis specifically requires them.

---

## 13. Real vs Mocked

| Capability / data | Real | Mocked / stubbed | UX treatment | Reason |
|---|---:|---:|---|---|
|  |  |  |  |  |

The interface must not present static/mock behavior as live behavior.

---

## 14. Acceptance Criteria

Acceptance criteria should be observable and traceable.

### Product / UX
- [ ] Primary actor can complete critical journey without facilitator explanation of UI.
- [ ] P0 requirements are represented.
- [ ] P0 provisional assumptions remain visible as provisional.
- [ ] Critical exceptions do not break comprehension.

### Design
- [ ] IA supports defined tasks.
- [ ] Critical flows and states are designed.
- [ ] Components/patterns are consistent.
- [ ] Target viewport behavior is defined.
- [ ] Accessibility behaviors are specified.

### Front-end
- [ ] Critical flow works end to end.
- [ ] Mock data is realistic and deterministic.
- [ ] Mocked capabilities are not misrepresented.
- [ ] Required loading/empty/error/attention states work.
- [ ] Keyboard path for critical task works.
- [ ] Build is stable in target environment.

---

## 15. Verification Plan

| Requirement / decision | Method | Artifact / check | Status |
|---|---|---|---|
| REQ- | inspection / analysis / demonstration / test |  | pending |

Important: verification asks whether we built the intended POC correctly. It is not equivalent to validation with real users.

---

## 16. Validation Status

### Available validation
- stakeholder evidence:
- technical evidence:
- user evidence:

### Not available
- 

Never claim user validation if no representative user was involved.

---

## 17. Risks and Open Decisions

| ID | Risk / question | Impact | Current handling | Blocks delivery? |
|---|---|---|---|---:|
| Q- |  |  | mock / assumption / exclude / investigate |  |

---

## 18. Delivery Artifacts

### Research / product
- `RESEARCH-BOARD.md`
- `REQUIREMENTS-LEDGER.md`
- `DOMAIN-MODEL.md`
- `CURRENT-JOURNEY.md`
- `FUTURE-JOURNEY.md`
- `POC-PRD.md`

### Design
- `IA.md`
- `TASK-FLOWS.md`
- `DESIGN-SPEC.md`
- prototype / design source

### Front-end
- `FRONTEND-SPEC.md`
- executable POC
- README/run instructions
- verification record

---

## 19. Definition of Done

The POC is deliverable when:

- [ ] source → claim → requirement traceability is recoverable;
- [ ] POC hypothesis and scope are explicit;
- [ ] design critical flows are complete;
- [ ] front-end reproduces the approved interaction model;
- [ ] real vs mocked behavior is explicit;
- [ ] acceptance criteria are satisfied or exceptions documented;
- [ ] known uncertainty remains visible;
- [ ] another agent can continue without reconstructing hidden reasoning.
