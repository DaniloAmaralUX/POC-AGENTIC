# POC-AGENTIC Process Changelog

This log records changes to the **generic POC process**, not normal changes inside individual POCs.

Use semantic intent rather than strict software semver:
- **Major** — changes stage order, core philosophy or required gates.
- **Minor** — adds a reusable stage, artifact, gate or agent rule.
- **Patch** — clarifies wording/templates without changing the method.

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