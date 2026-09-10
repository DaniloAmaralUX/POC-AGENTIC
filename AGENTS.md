# AGENTS.md — Operating Contract

This repository is designed to be read by AI agents and humans. Any agent working on a POC that uses this process must follow this contract.

## Start here

Before acting:

1. Read `README.md`.
2. Read `PROCESS.md`.
3. Read `GATES.md`.
4. Locate the target project folder.
5. Read its `RESEARCH-BOARD.md` and `POC-BRIEF.md` before proposing IA, UI or code.

If those artifacts do not exist, create the missing synthesis before continuing downstream.

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

## Agent behavior by phase

### Research / discovery

Do:
- read complete source material;
- preserve terminology from sources;
- separate fact from inference;
- record uncertainty;
- expose contradictions;
- ask only questions that materially affect the POC.

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

Do:
- design around the critical task;
- use the smallest future-state journey that tests the hypothesis;
- document why each major IA area exists;
- include empty/loading/error/exception states when they affect the tested journey.

Do not:
- default to `Dashboard / Users / Reports / Settings`;
- add features merely to make the POC look complete;
- polish secondary surfaces while critical uncertainty remains unresolved.

### Front-end

Do:
- preserve the approved task flow;
- use realistic content and data;
- mark stubs/mocks clearly;
- maintain basic accessibility and keyboard operation;
- keep abstractions proportional to actual reuse.

Do not:
- rewrite the product flow because implementation is easier;
- fabricate backend states;
- over-engineer infrastructure outside the POC learning goal.

### Validation

Do:
- test tasks and scenarios;
- record observed behavior;
- distinguish participant quote/behavior from interpretation;
- rank findings by impact on the hypothesis and task.

Do not:
- use aesthetic preference as the primary success metric;
- ask only whether participants “liked” the POC;
- convert one participant opinion into a universal rule.

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
- What is in and out of scope?
- What are the critical journeys?
- What is mocked vs. real?
- What stage/gate are we in?
- What should happen next?

If these answers are not recoverable from the repository, the handoff is incomplete.