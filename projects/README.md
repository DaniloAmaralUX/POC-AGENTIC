# Project Instances

Each real POC should live in its own folder under `projects/` or in its own product repository while referencing this repository as the canonical process.

A project instance contains **project evidence and decisions**. It must not redefine the generic method unless a reusable process change has been justified through Gate K.

## Recommended structure

```text
projects/<project-slug>/
  README.md
  RESEARCH-BOARD.md
  POC-BRIEF.md
  DOMAIN-MODEL.md
  CURRENT-JOURNEY.md
  SERVICE-BLUEPRINT.md       # when needed
  FUTURE-JOURNEY.md
  IA.md
  TASK-FLOWS.md
  VALIDATION-PLAN.md
  FINDINGS.md
  DECISION.md
```

## Project README minimum

```md
# <Project>

Current stage: <phase>
Current gate: <gate>
Process version: <POC-AGENTIC version>
Primary actor: <role>
Primary hypothesis: <one sentence>

## Source material
- <source>

## Current state
- What is known:
- What is assumed:
- What is blocked:

## Next action
<single clearest next action>
```

## Rules

- Copy templates when useful; do not copy `PROCESS.md` into every project.
- Project-specific exceptions belong in the project folder.
- Link important claims to source evidence where possible.
- Mark superseded artifacts rather than silently rewriting history when the change explains the current direction.
- Keep the current stage and next action explicit so an agent can resume work immediately.

## External project repository

A POC may live in another repository. In that case its root agent instructions should include:

```text
POC process source of truth:
https://github.com/DaniloAmaralUX/POC-AGENTIC

Required reading:
- AGENTS.md
- PROCESS.md
- GATES.md
```

Pin or record the process version used by the project. When the canonical process changes, do not automatically rewrite an active project's historical evidence; explicitly decide whether to adopt the newer process version.