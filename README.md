# POC-AGENTIC

A living, agent-readable process for turning incomplete or ambiguous product material into evidence-driven **design + front-end POCs**.

This repository is the canonical source of truth for the process. It is not a project template tied to one client. Any agent — Claude, Codex, ChatGPT or another coding/research agent — should be able to enter here, understand the method, know the current stage of a POC, identify what is evidence vs. hypothesis, and continue the work without inventing requirements.

## North Star

> Build the smallest credible product experience that proves, demonstrates or reduces uncertainty around the most important product hypothesis.

A POC is not a miniature final product. It is a controlled learning and delivery instrument.

## Core loop

```text
SOURCE MATERIAL
   ↓
EVIDENCE / CLAIMS
   ↓
REQUIREMENTS
   ↓
POC PRD
   ↓
DESIGN SPEC
   ↓
FRONT-END SPEC
   ↓
EXECUTABLE POC
   ↓
VERIFY
   ↓
LEARN
   ↓
UPDATE PROCESS
```

The detailed process lives in [`PROCESS.md`](./PROCESS.md).

## Non-negotiable rules

1. **Evidence before interface.** Do not jump from stakeholder material to screens.
2. **Facts, inferences, assumptions and open questions stay separate.** An agent must never silently promote an assumption to a fact.
3. **Requirements are traceable.** Important POC behavior should be connected to evidence, derivation or an explicit design hypothesis.
4. **The POC has one primary learning/demonstration goal.** Scope exists to answer a question, not to imitate product completeness.
5. **Domain before navigation.** Model objects, relationships and actors before freezing IA.
6. **Journeys before pages.** Design around critical tasks, not around a generic admin menu.
7. **PRD is a delivery contract, not a source of truth above evidence.** It summarizes the accepted baseline for design and implementation.
8. **Design and front-end are separate but traceable workstreams.** Front-end must preserve the approved interaction model or record a new decision.
9. **Front-end is part of the POC.** The build exists to make the concept credible and inspectable, not merely to reproduce screenshots.
10. **Uncertainty is visible.** Unknowns are documented instead of guessed.
11. **Verification is not user validation.** A POC may be well verified without claiming that end users validated it.
12. **Real POCs improve the method.** Reusable process learning updates this repository.

## Canonical files

- [`PROCESS.md`](./PROCESS.md) — current end-to-end POC method.
- [`EVIDENCE-TO-REQUIREMENTS.md`](./EVIDENCE-TO-REQUIREMENTS.md) — rules for turning source material into traceable requirements.
- [`AGENTS.md`](./AGENTS.md) — operating contract for any agent entering the repository.
- [`GATES.md`](./GATES.md) — decision gates before advancing stages.
- [`EVALS.md`](./EVALS.md) — regression/evaluation model for the agentic process.
- [`templates/RESEARCH-BOARD.md`](./templates/RESEARCH-BOARD.md) — evidence, facts, assumptions, questions, actors and domain.
- [`templates/REQUIREMENTS-LEDGER.md`](./templates/REQUIREMENTS-LEDGER.md) — atomic requirement baseline and traceability.
- [`templates/POC-BRIEF.md`](./templates/POC-BRIEF.md) — hypothesis and scope before full delivery definition.
- [`templates/PRD.md`](./templates/PRD.md) — canonical product/delivery contract for the POC.
- [`templates/DESIGN-SPEC.md`](./templates/DESIGN-SPEC.md) — design workstream contract from IA through interaction/state/accessibility handoff.
- [`templates/FRONTEND-SPEC.md`](./templates/FRONTEND-SPEC.md) — executable front-end workstream contract, mocks, state/data and verification traceability.
- [`templates/VALIDATION-PLAN.md`](./templates/VALIDATION-PLAN.md) — usability/research validation plan when representative users are available.
- [`CHANGELOG.md`](./CHANGELOG.md) — records reusable changes to the method itself.

## How an agent should start

```text
1. Read AGENTS.md
2. Read PROCESS.md
3. Locate the target project
4. Inspect its source manifest / Research Board
5. Check Facts / Inferences / Assumptions / Open Questions
6. Inspect Requirements Ledger
7. Identify current gate
8. Continue from the latest accepted artifact
9. Keep design and implementation traceable upstream
10. Update CHANGELOG.md only if the generic process itself improved
```

## Standard delivery chain

```text
RESEARCH-BOARD
      ↓
REQUIREMENTS-LEDGER
      ↓
POC-BRIEF
      ↓
POC-PRD
      ↓
DOMAIN / JOURNEYS / IA / TASK FLOWS
      ↓
DESIGN-SPEC
      ↓
FRONTEND-SPEC
      ↓
EXECUTABLE POC
      ↓
VERIFICATION / FINDINGS / DECISION
```

The PRD is not allowed to invent requirements. The Design Spec is not allowed to invent product capabilities. The Front-End Spec is not allowed to silently redesign the approved flow.

## Methodological references

Established requirements engineering, systems engineering and UX methods may support the process. Current references include Nielsen Norman Group material plus requirements/traceability practices documented in the repository.

External methodology informs the process; it never overrides project evidence.

## Process version

**v1.1 — 2026-09-10**

v1.1 formalizes the missing delivery bridge: a canonical POC PRD plus separate Design Spec and Front-End Spec so product understanding, interface definition and executable implementation remain distinct and traceable.