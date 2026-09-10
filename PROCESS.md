# Canonical POC Process

**Process version:** v0.1  
**Status:** living standard  
**Last updated:** 2026-09-10

This file is the canonical method. If the POC process evolves, update this file first and record the change in `CHANGELOG.md`.

## Purpose

Transform incomplete, ambiguous or stakeholder-led input into the smallest credible product experience that can be tested with users and stakeholders.

The process is optimized for agentic work: every stage produces explicit artifacts, evidence status and an exit gate so another agent can resume without reconstructing hidden reasoning.

---

## Phase 0 — Intake and Evidence Inventory

### Goal
Understand what material actually exists before interpreting it.

### Inputs
Examples:
- stakeholder interviews;
- meeting transcripts;
- briefs;
- screenshots;
- existing systems;
- technical documentation;
- analytics;
- regulations;
- competitor/reference material;
- user interviews.

### Agent actions
1. Read all source material.
2. Record each source in an evidence inventory.
3. Separate source-derived statements from inference.
4. Note source quality and perspective: stakeholder, user, technical, quantitative, legal, etc.
5. Do not resolve contradictions silently.

### Output
Research Board: Evidence section.

### Exit gate
There is enough material to state what is known, what is assumed and what is unknown.

---

## Phase 1 — Research Synthesis

### Goal
Convert raw material into an explicit understanding of the problem space.

### Required structure

#### Facts
Directly supported by evidence.

#### Assumptions
Plausible interpretations that are not yet validated.

#### Open Questions
Unknowns that can materially affect product, UX, business or technical decisions.

#### Risks
Consequences of being wrong.

### Rule
> No assumption may become a fact because it appears repeatedly in agent-generated documents.

### Output
`RESEARCH-BOARD.md`

### Exit gate
The team can explain the product problem without describing screens.

---

## Phase 2 — Actors and Stakeholders

### Goal
Understand who participates in the system and who actually uses the proposed experience.

### Distinguish
- stakeholder;
- primary user;
- secondary user;
- operator;
- administrator;
- support/implementation actor;
- external system or organization.

Do not invent personas with demographics unless supported by research. Prefer functional actors until real user evidence exists.

### Output
Actor map + stakeholder map.

### Exit gate
There is a defensible primary actor for the POC.

---

## Phase 3 — Domain Model

### Goal
Understand the system as objects and relationships before turning it into navigation.

### Identify
- core entities;
- relationships;
- optional vs. required relationships;
- lifecycle/state;
- ownership;
- data sources;
- external IDs;
- sensitive data;
- boundaries with external systems.

### Questions
- What exists independently?
- What produces events?
- What belongs to what?
- What can exist without another entity?
- What changes state?
- Which relationships are assumptions?

### Output
Domain Model v0.x.

### Exit gate
The team can model the core scenario without page names.

---

## Phase 4 — Current-State Journey

### Goal
Understand how the user achieves the relevant outcome today.

### Capture
- trigger;
- actions;
- systems/touchpoints;
- delays;
- handoffs;
- workarounds;
- pain/friction;
- consequence;
- evidence supporting each important claim.

### Rule
Current-state journey describes what exists, not the proposed solution.

### Output
Current-state journey map.

### Exit gate
The primary friction can be stated as a user/workflow problem rather than a feature request.

---

## Phase 5 — Service Blueprint

Use when the experience depends on multiple channels, devices, teams, integrations or backstage processes.

### Layers
1. User/customer actions.
2. Frontstage touchpoints.
3. Backstage systems/processes.
4. Support processes/dependencies.

### Purpose
Prevent interface design from hiding integration, operational or organizational problems.

### Output
Service Blueprint v0.x.

### Exit gate
Critical backstage dependencies and failure points are visible.

---

## Phase 6 — Research Validation

### Goal
Challenge stakeholder-derived assumptions with direct user or operational evidence.

### Preferred sequence for an early POC
1. Primary user interview.
2. Operator/secondary user interview where relevant.
3. Technical/implementation interview where system behavior matters.

### Interview principle
Ask about real past behavior before hypothetical future preference.

Prefer:
> “Tell me about the last time you had to investigate this.”

Over:
> “Would you use a dashboard for this?”

### Output
Updated Research Board + evidence-backed changes.

### Exit gate
The primary user, job and critical friction are credible enough to scope a POC.

---

## Phase 7 — Future-State Hypothesis

### Goal
Describe the smallest improved journey worth testing.

This is explicitly a hypothesis, not a requirement list.

### Structure
- trigger;
- user intent;
- expected system response;
- decision points;
- exception paths;
- desired outcome;
- assumptions still unresolved.

### Rule
Do not add features merely because they are typical in SaaS/admin products.

### Output
Future-state journey v0.x.

### Exit gate
The journey can be tested as a coherent end-to-end scenario.

---

## Phase 8 — POC Definition

### Goal
Choose the smallest vertical slice that tests the most important hypothesis.

Use `templates/POC-BRIEF.md`.

### Define
- problem statement;
- primary actor;
- hypothesis;
- learning goal;
- scenario;
- in scope;
- out of scope;
- success evidence;
- constraints;
- known fake/stubbed data;
- what must be real.

### POC rule
> Scope is determined by the question the POC must answer.

Not by:
- completeness;
- stakeholder wishlists;
- generic SaaS conventions;
- number of available development days.

### Exit gate
A reviewer can explain what the POC proves if it succeeds and what is learned if it fails.

---

## Phase 9 — Information Architecture

### Goal
Organize information around user tasks and domain relationships.

### Inputs
- validated actors;
- domain model;
- critical journeys;
- POC scope.

### Avoid
Starting with generic navigation such as:
`Dashboard / Users / Reports / Settings`
unless research actually supports those concepts.

### Output
IA v0.x with rationale.

### Exit gate
Every top-level area supports a known task or domain concept.

---

## Phase 10 — Critical Task Flows

### Goal
Define how the primary user completes the POC scenarios.

Each task flow should state:
- entry condition;
- user goal;
- decisions;
- success path;
- important error/empty/loading states;
- completion condition.

Prioritize 1–3 critical flows for a POC.

### Output
Task flows.

### Exit gate
The POC can be tested as tasks, not merely browsed as screens.

---

## Phase 11 — Prototype

### Goal
Create the minimum interface fidelity needed to test the hypothesis.

### Design principles
- content and data should look realistic;
- critical states must exist;
- avoid polishing parts outside the hypothesis;
- preserve uncertainty in annotations;
- use a system/component foundation where possible;
- design desktop/mobile only when relevant to the tested context.

### Output
Testable prototype or coded interaction slice.

### Exit gate
A participant can attempt the critical tasks without facilitator explanation of the UI.

---

## Phase 12 — Front-End POC

### Goal
Turn the validated interaction model into a credible executable vertical slice.

Front-end is part of product validation, not a separate handoff artifact.

### Requirements
- preserve the tested user flow;
- use realistic states/data;
- explicitly mark mocked integrations;
- no fake claims of real-time/backend behavior;
- keyboard and basic accessibility must work;
- responsive behavior must match target context;
- reusable components should emerge from repeated need, not premature abstraction.

### Agent rule
Before coding, read:
1. Research Board;
2. POC Brief;
3. task flows;
4. design decisions;
5. technical constraints.

### Exit gate
The vertical slice is stable enough for representative usability testing.

---

## Phase 13 — Usability / Concept Validation

### Goal
Test the proposed experience against representative tasks.

Do not primarily ask:
> “Do you like it?”

Ask participants to perform scenarios.

### Observe
- task success;
- wrong turns;
- hesitation;
- terminology problems;
- missing information;
- unexpected mental models;
- false confidence;
- workarounds;
- what they expect to happen next.

Use `templates/VALIDATION-PLAN.md`.

### Output
Findings ranked by impact and evidence.

### Exit gate
There is enough evidence to decide: iterate, expand, pivot or stop.

---

## Phase 14 — Synthesis and Decision

### Decision options
- **Proceed** — hypothesis supported strongly enough for next scope.
- **Iterate** — core hypothesis remains plausible but experience needs correction.
- **Pivot** — evidence changes user/problem/solution direction.
- **Stop** — hypothesis not valuable or feasible enough to continue.

Record:
- what was learned;
- what changed;
- what remains unknown;
- what should be tested next;
- which artifacts are now obsolete.

---

## Phase 15 — Compound the Learning

A POC should leave the next POC easier to execute.

After each project:
1. identify reusable research patterns;
2. identify reusable templates/components/scripts;
3. document mistakes and corrections;
4. distinguish project-specific knowledge from process knowledge;
5. update this repository only when the process itself improved.

### Governance rule
If a process change is supported by actual project learning:

```text
OBSERVATION
  ↓
PROPOSED PROCESS CHANGE
  ↓
UPDATE PROCESS.md / templates
  ↓
UPDATE AGENTS.md if agent behavior changes
  ↓
ADD CHANGELOG ENTRY
```

Do not update the canonical method just because one project had a special case.

---

# Minimum artifact set per POC

```text
projects/<project>/
  README.md
  RESEARCH-BOARD.md
  POC-BRIEF.md
  DOMAIN-MODEL.md
  CURRENT-JOURNEY.md
  SERVICE-BLUEPRINT.md        # when needed
  FUTURE-JOURNEY.md
  IA.md
  TASK-FLOWS.md
  VALIDATION-PLAN.md
  FINDINGS.md
  DECISION.md
```

The project may use fewer files if the same information remains explicit and agent-readable.

# Methodological support

Use established UX methods as supporting process references. A starting reference library is Nielsen Norman Group reports and research material:

https://www.nngroup.com/reports/

External methodology does not override observed project evidence.