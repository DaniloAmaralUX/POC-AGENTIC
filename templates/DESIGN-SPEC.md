# Design Spec — <PROJECT>

**Version:** 0.1  
**Status:** Draft | Ready for Build | Superseded  
**Date:** YYYY-MM-DD

> The Design Spec translates validated/provisional product requirements into a testable interaction model. It must preserve uncertainty and must not invent backend capabilities.

---

## 1. Design Objective

### Primary actor
<role>

### Primary task
<task>

### POC hypothesis supported
> <hypothesis>

### Design question
> Can the user understand and complete <critical outcome> through this interaction model?

---

## 2. Upstream Inputs

Required before design begins:
- Research Board
- Requirements Ledger
- Domain Model
- POC PRD
- Current Journey
- Future Journey

Record the exact paths/versions used.

---

## 3. Critical Journeys

For each journey define:
- trigger;
- entry point;
- user goal;
- happy path;
- decision points;
- exception states;
- completion state.

Limit a POC to the smallest set necessary for the hypothesis.

---

## 4. Information Architecture

Document:
- top-level areas;
- rationale for each area;
- relationship to domain concepts;
- relationship to user tasks;
- deferred areas.

Every major IA element must trace to a requirement, domain concept or explicit design hypothesis.

---

## 5. Screen / Surface Inventory

| ID | Surface | Purpose | Journey | Requirement / Hypothesis | Priority |
|---|---|---|---|---|---|
| UI-001 |  |  | J-001 | REQ- / DH- | P0 |

Do not create one screen per entity by default.

---

## 6. Interaction Model

For every critical surface capture:
- primary action;
- secondary actions;
- navigation behavior;
- selection behavior;
- filtering/search behavior;
- destructive behavior;
- feedback;
- persistence expectation;
- keyboard behavior where relevant.

---

## 7. State Matrix

| Surface / component | Default | Loading | Empty | Error | Success | Attention / Exception | Permission |
|---|---:|---:|---:|---:|---:|---:|---:|
|  | ✓ |  |  |  |  |  |  |

Only include states that matter to the POC task, but do not omit a state if its absence could create a false product claim.

---

## 8. Content Model

### Terminology
Use project/source terminology where evidence exists.

### Realistic data
Define representative data values required for comprehension.

### Sensitive content
Identify PII/regulated fields and whether they are shown, masked, anonymized or omitted.

---

## 9. Visual System

### Foundation
- design system / component library used;
- typography;
- spacing/radius;
- color semantics;
- iconography;
- data visualization conventions, if relevant.

### Rule
Visual polish must support the tested task. It must not hide unresolved product logic.

---

## 10. Component / Pattern Inventory

| Pattern | Existing / New | Why needed | Reuse scope |
|---|---|---|---|
|  |  |  | POC / shared |

Avoid premature abstraction. Reusable patterns should emerge from repeated need.

---

## 11. Responsive Strategy

### Target contexts
- Primary viewport/context:
- Secondary viewport/context:
- Explicitly out of scope:

Define behavior rather than just screenshots:
- content priority;
- stacking;
- navigation change;
- table/list behavior;
- overflow handling;
- touch target considerations.

---

## 12. Accessibility Behavior

Minimum:
- keyboard path for critical task;
- visible focus;
- semantic labels;
- meaningful heading hierarchy;
- non-color cues for status;
- contrast appropriate to role;
- form errors tied to fields;
- accessible names for icon-only actions;
- reduced motion where motion is used.

---

## 13. Motion / Feedback

Use motion only when it explains:
- state change;
- hierarchy;
- continuity;
- cause/effect.

Document any critical transitions. Avoid decorative motion that interferes with inspection/testing.

---

## 14. Mock / Real Disclosure

For every surface that implies backend or live behavior:

| UI behavior | Real or Mocked | User-facing treatment | Implementation note |
|---|---|---|---|
|  |  |  |  |

Do not design fake real-time states as if they were connected.

---

## 15. Design Decisions

Use explicit decisions:

```yaml
id: DD-001
decision: ""
rationale: ""
upstream:
  - REQ-
  - DH-
alternatives_considered: []
status: accepted | provisional | superseded
```

---

## 16. Design QA

Before handoff/build:
- [ ] every P0 requirement has UI coverage or explicit non-UI handling;
- [ ] every major screen has an upstream rationale;
- [ ] critical journey works end to end;
- [ ] key states are designed;
- [ ] mock behavior is identifiable;
- [ ] terminology matches evidence/glossary;
- [ ] accessibility behaviors are specified;
- [ ] target responsive behavior is defined;
- [ ] unresolved assumptions remain labeled;
- [ ] no generic SaaS feature appeared without rationale.

---

## 17. Handoff to Front-End

The front-end agent/team receives:
- POC PRD;
- Requirements Ledger;
- this Design Spec;
- task flows;
- prototype/design source;
- component/state inventory;
- realistic data fixtures/content;
- technical constraints;
- explicit mocks.

If implementation requires changing a critical flow, update the design decision first. Do not silently redesign in code.

---

## 18. Design Readiness Gate

Ready for build when:
- [ ] primary flow is coherent;
- [ ] P0 surfaces/states are covered;
- [ ] interaction rules are explicit;
- [ ] responsive target is known;
- [ ] accessibility essentials are known;
- [ ] real vs mocked behavior is explicit;
- [ ] major design decisions are traceable.
