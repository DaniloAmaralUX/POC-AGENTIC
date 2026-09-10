# Paperclip Adapter for POC-AGENTIC

This adapter maps the canonical `POC-AGENTIC` method to Paperclip without changing the method itself.

Paperclip is an orchestration layer. `PROCESS.md`, `AGENTS.md`, `GATES.md`, the project artifacts and source evidence remain authoritative.

## Use case

Use this adapter when a POC will be executed by multiple specialized agents coordinated through Paperclip.

Recommended default topology:

```text
HUMAN BOARD
   ↓
POC LEAD / CEO
   ├── Evidence & Requirements Engineer
   ├── Product / UX Design Engineer
   ├── Front-end Engineer
   └── POC Reviewer / Quality Judge
```

Keep the team small. Add a specialist only when a real bottleneck or domain need appears.

## Operating model

```text
SOURCE MATERIAL
   ↓
Evidence & Requirements
   ↓
REVIEW / GATE
   ↓
POC PRD
   ↓
REVIEW / GATE
   ↓
Product / UX Design
   ↓
REVIEW / GATE
   ↓
Front-end
   ↓
REVIEW / VERIFICATION
   ↓
Human decision
```

The CEO coordinates work and gates. It does not silently reinterpret the process.

## Paperclip work modes

Use the mode that matches the deliverable:

- **Ask** — answer a bounded question; no artifact/change required.
- **Plan** — propose an approach for review before execution.
- **Agent / Standard** — produce or modify artifacts, code, configuration or other durable work.

Deep research that must leave a traceable document is standard work, not Ask mode.

## Workspace policy

For code/file work, prefer isolated workspaces when parallel work would otherwise touch the same checkout.

Do not use isolated workspaces as a reason to parallelize tightly coupled stages. Research → requirements → PRD → design → front-end remains dependency-aware.

## Canonical-read contract

Every Paperclip agent must begin by reading:

1. repository `AGENTS.md`;
2. `PROCESS.md`;
3. `GATES.md`;
4. the target project's latest accepted artifacts;
5. its own role card in `ROLE-CARDS.md`.

The front-end agent must additionally read the current PRD, task flows, Design Spec and Front-End Spec before coding.

## Human approval points

The human board should approve at minimum:

1. POC hypothesis and scope baseline;
2. PRD baseline;
3. design direction / critical flows before significant build;
4. final delivery decision.

Do not allow an autonomous chain to promote assumptions to facts just because no human intervened.

## Cost control

Start with conservative company and per-agent budgets. Prefer wake-on-assignment or deliberate task runs while validating the workflow. Avoid continuous high-frequency heartbeats for a POC unless there is a demonstrated need.

## Repository separation

Recommended:

```text
POC-AGENTIC
  = canonical method

<PROJECT>-POC
  = one project execution
```

The execution repository should point back to `POC-AGENTIC` rather than copying and diverging the method.

## Files in this adapter

- `COMPANY-GOAL.md` — reusable company goal template.
- `CEO-INSTRUCTIONS.md` — operating instructions for the Paperclip CEO/POC Lead.
- `ROLE-CARDS.md` — bounded responsibilities for the four default agents.
- `ISSUE-PLAN.md` — dependency-aware task plan mapped to POC gates.

## Rule

> Paperclip coordinates the process. It does not become the process.
