# AGENTS.md — Operating Contract

This repository is designed to be read by AI agents and humans. Any agent working on a POC that uses this process must follow this contract.

## Start here

Before acting:

1. Read `README.md`.
2. Read `PROCESS.md`.
3. Read `GATES.md`.
4. Locate the target project folder.
5. Read the latest accepted project artifacts for the current phase.

### Required artifact chain by phase

Before product definition:
- `RESEARCH-BOARD.md`
- `REQUIREMENTS-LEDGER.md`
- `DOMAIN-MODEL.md`

Before design:
- all above;
- `POC-BRIEF.md`;
- `POC-PRD.md`;
- `FUTURE-JOURNEY.md`;
- `TASK-FLOWS.md` when already available.

Before front-end:
- all above;
- `DESIGN-SPEC.md`;
- approved prototype/design source;
- technical constraints.

Before verification:
- `FRONTEND-SPEC.md`;
- runnable/deployed POC;
- requirements traceability.

If required artifacts do not exist, create or complete the missing upstream synthesis before inventing downstream decisions.

---

## Evidence discipline

Every important statement must be classified as one of:

- **FACT** — directly supported by source evidence.
- **ASSUMPTION** — plausible but unvalidated.
- **OPEN QUESTION** — materially unknown.
- **DECISION** — an explicit product/design/technical choice.
- **INFERENCE** — interpretation derived from one or more facts.

### Never do this

- convert stakeholder opinion into user fact;
- fill an unknown with a generic SaaS pattern;
- cite an agent-generated document as evidence for a claim that originated as an assumption;
- silently resolve contradictory source material;
- invent technical capabilities because the UI would benefit from them;
- describe mocked behavior as real integration.

---

## Requirement discipline

Use `EVIDENCE-TO-REQUIREMENTS.md` and `templates/REQUIREMENTS-LEDGER.md`.

Each P0 requirement must have:
- source/derivation;
- epistemic/origin status;
- rationale;
- observable fit criterion;
- verification method;
- scope.

A design hypothesis is not silently promoted into a requirement.
A reference pattern is not a requirement simply because competitors use it.

---

## PRD discipline

The POC PRD is a **delivery contract**, not a new evidence source.

It must summarize/reference:
- evidence basis;
- primary actor;
- problem/hypothesis;
- requirements baseline;
- product boundary;
- critical journeys;
- in/out scope;
- real vs mocked behavior;
- acceptance criteria;
- design and front-end delivery contracts.

Do not use the PRD to hide uncertainty already visible upstream.

---

## Agent behavior by phase

### Research / discovery

Do:
- read complete source material;
- preserve terminology from sources;
- separate fact from inference;
- record uncertainty;
- expose contradictions;
- identify only questions that materially affect the POC.

Do not:
- jump to wireframes;
- create personas with fictional demographics;
- infer business rules from common product conventions.

### Modeling

Do:
- model actors, entities, relationships and states;
- mark optional/required relationships;
- connect every critical concept to evidence or mark it as hypothesis.

Do not:
- make navigation the domain model;
- assume one page per entity.

### Product / UX design

Read `templates/DESIGN-SPEC.md`.

Do:
- design around critical tasks;
- use the smallest future-state journey that supports the POC;
- document why each major IA area exists;
- cover meaningful default/loading/empty/error/attention states;
- specify interaction behavior, responsive behavior and accessibility;
- trace major surfaces/decisions to requirements or explicit hypotheses;
- disclose mocked/live behavior in the design.

Do not:
- default to `Dashboard / Users / Reports / Settings`;
- add features merely to make the POC look complete;
- polish secondary surfaces while critical logic is unresolved;
- invent backend behavior to make a screen convenient.

### Front-end

Read `templates/FRONTEND-SPEC.md`.

Do:
- preserve the approved task flow;
- use realistic deterministic content/data;
- mark stubs/mocks clearly;
- implement the states required by the POC;
- maintain basic accessibility and keyboard operation;
- keep abstractions proportional to actual reuse;
- document routes, data fixtures, interactions and deployment/run instructions;
- trace P0 implementation to requirements/design.

Do not:
- rewrite the product flow because implementation is easier;
- fabricate backend states;
- present static fixture data as real-time integration;
- over-engineer infrastructure outside the POC goal.

If implementation requires a material design/product change, create a decision and update the upstream artifact before proceeding.

### Validation / verification

Do:
- distinguish verification from user validation;
- test tasks/scenarios when representative users exist;
- record observed behavior separately from interpretation;
- use inspection/demonstration/analysis when user access is unavailable;
- rank findings by impact on requirement/hypothesis/task.

Do not:
- use aesthetic preference as the primary success metric;
- claim user validation without representative users;
- convert one reviewer opinion into a universal rule.

---

## Gate discipline

An agent may not advance a POC simply because downstream work is possible.

Before moving phases, check `GATES.md`.

If a gate fails:
- state why;
- identify the minimum missing evidence or decision;
- stop or continue only with the affected part explicitly labeled as provisional.

---

## Updating the canonical process

The repository is a living standard.

Update `PROCESS.md` only when learning from a real POC indicates the generic process itself should change.

When changing the process:

1. explain the observed problem;
2. explain the new rule/process;
3. update affected templates;
4. update this file if agent behavior changes;
5. add an entry to `CHANGELOG.md`;
6. preserve project-specific exceptions inside the project, not the global method.

### Change test

Before modifying the process, ask:

> “Would this improve how we run multiple future POCs, or is it only true for this project?”

Only the first case belongs in the canonical process.

---

## File writing conventions

Prefer Markdown.

For decision-sensitive sections, use explicit status labels:

```text
[F] FACT
[A] ASSUMPTION
[Q] OPEN QUESTION
[D] DECISION
[I] INFERENCE
```

When possible, include source references next to facts.

Use dates and versions on major project artifacts.

Do not delete obsolete decisions silently. Mark them superseded or preserve them in history when they explain current direction.

---

## Definition of a good agent handoff

Another agent should be able to answer, without asking the previous agent:

- What problem are we trying to understand?
- Who is the primary actor?
- What evidence do we have?
- What is still assumed?
- What is unknown?
- What is the POC hypothesis?
- Which requirements are in the baseline?
- What is in and out of scope?
- What are the critical journeys?
- What is the approved interaction model?
- What is mocked vs. real?
- What exactly must design deliver?
- What exactly must front-end implement?
- What stage/gate are we in?
- What should happen next?

If these answers are not recoverable from the repository, the handoff is incomplete.