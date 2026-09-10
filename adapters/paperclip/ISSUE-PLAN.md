# Paperclip Issue Plan for a POC

Use this as a dependency-aware starting plan. Do not create all issues blindly; the CEO should adapt it to the target project's current gate and evidence.

## Stage 1 — Evidence and requirements

```text
PAP-01  Intake + source manifest
PAP-02  Atomic claim extraction
PAP-03  Research synthesis / CSD
PAP-04  Actor + stakeholder map
PAP-05  Domain + operational model
PAP-06  Current-state journey / service blueprint
PAP-07  Requirements ledger
PAP-08  Skeptic review of evidence + requirements
PAP-09  Revise requirement baseline
```

Gate: evidence and requirements ready.

## Stage 2 — Product baseline

```text
PAP-10  POC Brief
PAP-11  POC PRD
PAP-12  PRD / scope review
```

Human approval: POC hypothesis, scope and PRD baseline.

## Stage 3 — Product / UX design

```text
PAP-13  Future-state journey
PAP-14  Information architecture
PAP-15  Critical task flow 1
PAP-16  Critical task flow 2
PAP-17  Critical task flow 3 (only if needed)
PAP-18  Surface + state inventory
PAP-19  High-fidelity interaction design
PAP-20  Design Spec
PAP-21  Design traceability / accessibility review
PAP-22  Design corrections
```

Human approval: critical experience before significant front-end build.

## Stage 4 — Front-end POC

```text
PAP-23  Front-end architecture + fixture strategy
PAP-24  Front-End Spec baseline
PAP-25  Implement app shell / shared primitives
PAP-26  Implement critical flow 1
PAP-27  Implement critical flow 2
PAP-28  Implement critical flow 3 (only if needed)
PAP-29  Required loading / empty / error / attention states
PAP-30  Responsive + keyboard + accessibility pass
PAP-31  Visual/design QA
PAP-32  Build / lint / test / preview verification
PAP-33  Correct implementation drift
```

## Stage 5 — Verification and decision

```text
PAP-34  Requirements verification matrix
PAP-35  Scenario walkthrough / cognitive inspection
PAP-36  Final POC review
PAP-37  Findings + known limitations
PAP-38  Proceed / Iterate / Pivot / Stop recommendation
PAP-39  Identify reusable process learning
```

If PAP-39 reveals a generic improvement, update `POC-AGENTIC` and add an eval case where useful.

## Dependency rule

Do not treat this as a waterfall ceremony. Parallelize work only when dependencies permit it.

Examples:
- source extraction from independent documents can run in parallel;
- IA and domain clarification may iterate together after requirements are stable enough;
- front-end foundation can start after the core interaction contract is stable, but critical flow implementation must not outrun unresolved product decisions;
- Reviewer can inspect continuously but should gate baselines at explicit checkpoints.

## Issue completion rule

An issue is not done because text or code was produced. It is done when its artifact is reviewable, traceable and meets the relevant gate/acceptance criterion.
