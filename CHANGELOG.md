# POC-AGENTIC Process Changelog

This log records changes to the **generic POC process**, not normal changes inside individual POCs.

Use semantic intent rather than strict software semver:
- **Major** — changes stage order, core philosophy or required gates.
- **Minor** — adds a reusable stage, artifact, gate or agent rule.
- **Patch** — clarifies wording/templates without changing the method.

---

## v1.2 — 2026-09-10

### Problem observed
The canonical process was agent-readable but did not yet define how an external agent orchestrator should coordinate specialized roles, gates and artifacts without becoming a second competing methodology.

### Evidence
The AGS Diagnósticos POC was selected as the first real Paperclip experiment. The project needs evidence extraction, requirements engineering, Product/UX Design, front-end implementation and independent review, but these stages must remain governed by the existing `POC-AGENTIC` evidence and gate model.

### Process change
- Added an optional Paperclip orchestration adapter under `adapters/paperclip/`.
- Defined the default four-agent topology: Evidence & Requirements Engineer, Product / UX Design Engineer, Front-end Engineer and POC Reviewer / Quality Judge, coordinated by a CEO / POC Lead.
- Added a reusable company-goal template.
- Added CEO instructions with authority hierarchy, gate behavior, delegation boundaries, mock/real rules and completion criteria.
- Added bounded role cards to prevent responsibility overlap and agent scope drift.
- Added a dependency-aware issue plan from evidence work through final verification.
- Formalized the rule that orchestration tools coordinate the canonical process but do not override evidence, requirements, gates or human decisions.

### Files affected
- `README.md`
- `adapters/paperclip/README.md`
- `adapters/paperclip/COMPANY-GOAL.md`
- `adapters/paperclip/CEO-INSTRUCTIONS.md`
- `adapters/paperclip/ROLE-CARDS.md`
- `adapters/paperclip/ISSUE-PLAN.md`
- `CHANGELOG.md`

### Why this is reusable
Future POCs may use Paperclip or another multi-agent coordinator. Separating orchestration from methodology allows the same evidence-to-design-to-front-end process to survive changes in tooling while still giving agents explicit operating boundaries.

---

## v1.1 — 2026-09-10

### Problem observed
The process already described design and front-end phases, but there was no canonical artifact making the handoff between evidence/requirements, interface design and executable implementation explicit.

That leaves room for three recurring agent failures:
- the PRD becoming an untraceable feature wishlist;
- design inventing product/backend behavior not established upstream;
- front-end silently changing the approved interaction model because implementation convenience differs from the design.

### Evidence
While preparing AGS Diagnósticos for a real design + front-end delivery, the repository had Research Board, Requirements Ledger, POC Brief and Validation Plan templates, but no canonical POC PRD, Design Spec or Front-End Spec.

### Process change
- Added `templates/PRD.md` as the delivery contract that summarizes evidence, baseline requirements, POC scope, journeys, real-vs-mocked behavior, acceptance criteria and downstream delivery expectations.
- Added `templates/DESIGN-SPEC.md` for IA, surfaces, state matrix, interaction rules, content, accessibility, responsive behavior, design decisions and handoff.
- Added `templates/FRONTEND-SPEC.md` for route, data, fixture, state, interaction, component, accessibility, responsive, deployment and verification contracts.
- Updated the canonical chain to `Evidence → Requirements → PRD → Design Spec → Front-End Spec → Executable POC → Verification`.
- Added explicit design-to-front-end traceability and implementation-drift rules.
- Updated `AGENTS.md` so agents read different required artifacts depending on the phase.
- Updated README and minimum artifact set.

### Files affected
- `PROCESS.md`
- `AGENTS.md`
- `README.md`
- `templates/PRD.md`
- `templates/DESIGN-SPEC.md`
- `templates/FRONTEND-SPEC.md`
- `CHANGELOG.md`

### Why this is reusable
Every future POC delivered as both design and executable front-end needs a stable boundary between what the product must demonstrate, how the interaction is intended to work and how the implementation realizes it. The split prevents upstream uncertainty from being hidden in UI or code and makes handoffs recoverable by any agent.

---

## v1.0 — 2026-09-10

### Problem observed
The real operating model for these POCs does not guarantee direct access to clients or end users. The team may receive only requirement lists, PDFs, transcripts, screenshots and technical/reference material, then must convert that corpus into a credible design/front-end POC.

The v0.1 process assumed direct research validation as a normal intermediate phase. That created a mismatch between the canonical method and the actual delivery constraint.

### Evidence
AGS Diagnósticos exposed the issue: a rich stakeholder transcript was enough to reconstruct business intent, equipment/integration context and candidate workflows, but not enough to claim observed user needs or behavior.

### Process change
- Adopted **evidence-constrained POC mode** as a first-class operating path.
- Added explicit Source → Claim → Requirement → Decision → Flow/UI → Verification traceability.
- Added atomic claim extraction before requirements generation.
- Incorporated CSD logic for Certainties / Suppositions / Doubts.
- Added requirements origin taxonomy: Explicit / Derived / Provisional / Design Hypothesis / Reference Pattern.
- Added an atomic Requirements Ledger with rationale, source, assumption dependencies, fit criterion and verification method.
- Replaced mandatory direct-user research with an Evidence Challenge phase supporting two modes: direct research when available; triangulation/inspection when unavailable.
- Made verification vs validation explicit. A POC without representative-user contact must be labeled **not user-validated**.
- Added controlled agent workflow: Corpus Analyst → Evidence Extractor → Domain Modeler → Requirements Engineer → Skeptic → Reviser → Quality Judge → UX/Product Modeler → Builder.
- Added red-team/evaluator loop to prevent unsupported requirements and solution creep.
- Added `EVALS.md` so real extraction failures become regression cases for the process.
- Expanded gates to include Source Ready, Evidence Challenge, Requirements Grounding and Evaluation status.

### Files affected
- `PROCESS.md`
- `AGENTS.md`
- `GATES.md`
- `EVIDENCE-TO-REQUIREMENTS.md`
- `EVALS.md`
- `templates/REQUIREMENTS-LEDGER.md`
- `CHANGELOG.md`

### Methodological foundations added
- ISO/IEC/IEEE 29148 — requirements engineering lifecycle/process foundation.
- Volere — atomic requirements, rationale, fit criteria, facts/assumptions and work-vs-product scope.
- NASA/INCOSE systems engineering guidance — traceability, verification and validation concepts.
- IREB — requirements lifecycle and traceability concepts.
- Nielsen Norman Group — discovery, CSD matrix, task analysis, mapping and usability inspection methods.
- Agent-engineering guidance — sequential workflows, specialized roles, critic/reviser/evaluator patterns and eval-driven improvement.

### Why this is reusable
Any POC produced from incomplete or second-hand material faces the same epistemic risk: agents can produce plausible requirements that the source never established. The new pipeline makes provenance, uncertainty and verification part of the standard rather than project-specific cleanup.

---

## v0.1 — 2026-09-10

### Added
- Canonical evidence-driven POC process.
- Agent operating contract.
- Decision-gate system.
- Evidence inventory.
- Facts / Assumptions / Open Questions discipline.
- Actor and stakeholder mapping before persona invention.
- Domain modeling before information architecture.
- Current-state journey before future-state design.
- Service blueprint when multiple channels/systems/teams are involved.
- Explicit research validation between stakeholder synthesis and product commitment.
- Future-state as a hypothesis rather than a requirements document.
- POC Brief centered on one primary learning goal.
- IA and critical task flows before prototype/build.
- Front-end POC treated as a research instrument.
- Task-based usability validation.
- Proceed / Iterate / Pivot / Stop decision model.
- Gate K for changing the canonical process only from reusable real-project learning.

### Origin
Initial method was formalized while working through the AGS Diagnósticos POC. The project exposed the need to prevent stakeholder statements, agent inference and generic SaaS conventions from being silently converted into requirements.

### Supporting methodological reference
Nielsen Norman Group reports and UX research material are used as an auxiliary process reference:
https://www.nngroup.com/reports/

---

## How to add an entry

```text
## vX.Y — YYYY-MM-DD

### Problem observed
What happened in a real POC?

### Evidence
Which project/artifact/session exposed it?

### Process change
What generic rule, stage, gate or template changed?

### Files affected
- PROCESS.md
- AGENTS.md
- GATES.md
- templates/...

### Why this is reusable
Why should future POCs inherit this change?
```

Do not add project-specific feature decisions to this changelog.