# POC-AGENTIC

A living, agent-readable process for turning ambiguous product opportunities into evidence-driven **design + front-end POCs**.

This repository is the canonical source of truth for the process. It is not a project template tied to one client. Any agent — Claude, Codex, ChatGPT or another coding/research agent — should be able to enter here, understand the method, know the current stage of a POC, identify what is evidence vs. hypothesis, and continue the work without inventing requirements.

## North Star

> Build the smallest credible product experience that proves or disproves the most important product hypothesis.

A POC is not a miniature final product. It is a controlled learning instrument.

## Core loop

```text
UNDERSTAND
   ↓
SYNTHESIZE
   ↓
MODEL
   ↓
PRIORITIZE
   ↓
DESIGN
   ↓
BUILD
   ↓
VERIFY
   ↓
LEARN
   ↓
UPDATE
```

The detailed process lives in [`PROCESS.md`](./PROCESS.md).

## Non-negotiable rules

1. **Evidence before interface.** Do not jump from stakeholder conversation to screens.
2. **Facts, assumptions and open questions stay separate.** An agent must never silently promote an assumption to a fact.
3. **The POC has one primary learning goal.** Scope exists to answer a question, not to imitate product completeness.
4. **Domain before navigation.** Model the objects, relationships and actors before freezing IA.
5. **Journeys before pages.** Design around critical user tasks, not around a generic admin menu.
6. **Front-end is part of research.** The build exists to test the proposed experience, not merely to reproduce mockups.
7. **Uncertainty is visible.** Unknowns are documented instead of guessed.
8. **Validation changes the process.** When evidence shows the method itself should change, update this repository.

## Canonical files

- [`PROCESS.md`](./PROCESS.md) — current end-to-end POC method.
- [`AGENTS.md`](./AGENTS.md) — operating contract for any agent entering the repository.
- [`GATES.md`](./GATES.md) — decision gates before advancing stages.
- [`templates/RESEARCH-BOARD.md`](./templates/RESEARCH-BOARD.md) — evidence, facts, assumptions, questions, actors and domain.
- [`templates/POC-BRIEF.md`](./templates/POC-BRIEF.md) — defines the hypothesis and scope of a POC.
- [`templates/VALIDATION-PLAN.md`](./templates/VALIDATION-PLAN.md) — usability/research validation plan.
- [`CHANGELOG.md`](./CHANGELOG.md) — records changes to the method itself.

## How an agent should start

```text
1. Read AGENTS.md
2. Read PROCESS.md
3. Locate the current project's Research Board
4. Check Facts / Assumptions / Open Questions
5. Identify the current gate
6. Continue only from evidence that exists
7. Record new evidence and decisions
8. Update CHANGELOG.md if the process itself changed
```

## Methodological reference

The process is evidence-driven and uses established UX practices such as research synthesis, journey mapping, service blueprinting, information architecture, task-flow design and usability testing. Nielsen Norman Group reports and articles are a supporting methodological reference: https://www.nngroup.com/reports/

These references inform the process; they do not replace project evidence.

## Process version

**v0.1 — 2026-09-10**

Initial process distilled from the AGS Diagnósticos POC discovery work and formalized as a reusable workflow.