# Research Board — <PROJECT>

**Version:** 0.1  
**Status:** Draft / In Research / Validated / Superseded  
**Last updated:** YYYY-MM-DD

This is the evidence ledger for the POC. Keep source-derived knowledge separate from assumptions and agent inference.

---

## 1. Problem framing

### Current understanding
<Describe the problem without proposing a UI.>

### Primary learning question
<What do we need to understand before committing to a solution?>

---

## 2. Evidence inventory

| ID | Source | Type | Perspective | Date | Reliability / caveat | Key contribution |
|---|---|---|---|---|---|---|
| E1 |  | Stakeholder interview / user interview / technical doc / analytics / etc. |  |  |  |  |

---

## 3. Facts

Only statements directly supported by evidence.

- [F1] <Fact> — Evidence: E1
- [F2] <Fact> — Evidence: E2

---

## 4. Assumptions

Plausible but not validated.

| ID | Assumption | Why plausible | Risk if wrong | Validation method | Status |
|---|---|---|---|---|---|
| A1 |  |  |  |  | Open |

---

## 5. Open questions

Questions that can materially change product, UX, business or technical direction.

| ID | Question | Why it matters | Who/what can answer | Blocking? | Status |
|---|---|---|---|---|---|
| Q1 |  |  |  | Yes/No | Open |

---

## 6. Contradictions / tensions

Do not reconcile silently.

| ID | Statement A | Statement B | Source(s) | What must be clarified |
|---|---|---|---|---|
| C1 |  |  |  |  |

---

## 7. Actors

### Primary actor
- Role:
- Goal:
- Evidence level:
- Known tasks:
- Unknowns:

### Secondary actors
- <Actor> — role in system

### Stakeholders
- <Stakeholder> — influence / interest

### External systems / organizations
- <System> — boundary / dependency

---

## 8. Jobs / critical tasks

Do not invent JTBD language if behavior evidence is missing. Mark hypotheses.

### Evidence-backed
- <Task>

### Hypothesized
- [A#] <Task>

---

## 9. Domain model

### Entities
- Entity A
- Entity B
- Entity C

### Relationships
```text
ENTITY A
  └── has many → ENTITY B
                    └── may reference → ENTITY C
```

### Relationship uncertainty
- [A#] <relationship assumption>

### State/lifecycle
```text
STATE A → STATE B → STATE C
```

### Sensitive data
- <field / entity>
- Legal/privacy question: Q#

---

## 10. Current-state journey

### Scenario
<One real scenario.>

```text
TRIGGER
  ↓
ACTION
  ↓
TOUCHPOINT
  ↓
HANDOFF / DELAY
  ↓
OUTCOME
```

### Frictions
- FRICTION 1 — Evidence: E#
- FRICTION 2 — Evidence: E#

### Problem statement
> <State the user/workflow problem, not a feature request.>

---

## 11. Service blueprint

Use only if the journey depends on multiple channels, teams, devices or backstage processes.

### Customer / user actions
- 

### Frontstage
- 

### Backstage
- 

### Support processes
- 

### Failure points
- 

---

## 12. Future-state hypotheses

These are hypotheses until tested.

### H1
> If <change>, then <actor> can <outcome>, because <reason/evidence>.

Evidence basis:
Assumptions:
Validation:

---

## 13. Research plan

| Research question | Method | Participant/source | Evidence needed | Status |
|---|---|---|---|---|
|  |  |  |  |  |

---

## 14. Decisions

| ID | Decision | Why | Evidence / assumption | Date | Supersedes |
|---|---|---|---|---|---|
| D1 |  |  |  |  |  |

---

## 15. Current gate

Current gate: `Gate ?`

### Pass criteria already met
- 

### Missing before next gate
- 

### Next action
> <single clearest next action>
