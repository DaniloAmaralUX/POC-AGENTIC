# POC Decision Gates

These gates prevent downstream work from converting uncertainty into false certainty.

A gate is not bureaucracy. It is a checkpoint asking whether the next phase would increase learning or merely increase output.

## Gate A — Source Ready
Before evidence extraction.

Must be true:
- available source material has been read;
- source manifest exists;
- source perspective/type is identified;
- missing/garbled material is visible;
- contradictions are not silently resolved.

Fail if the agent is relying on snippets while full material exists or cannot say what evidence is available.

## Gate B — Evidence Ready
Before synthesis/modeling.

Must be true:
- important claims have source IDs/locators where possible;
- Facts, Inferences, Assumptions and Open Questions are separated;
- stakeholder statement is not conflated with user truth;
- major risks created by uncertainty are visible.

Fail if interpretation is hidden inside polished prose.

## Gate C — Problem Ready
Before domain/future-state work.

Must be true:
- problem can be explained without UI;
- primary actor is explicit and evidence level known;
- stakeholder and user are not conflated;
- the critical job/task is explicit or clearly marked provisional.

Fail if a feature request is being used as the whole problem definition.

## Gate D — Domain Ready
Before requirements baseline/IA.

Must be true:
- glossary/core entities exist;
- events/states and relationships are explicit where relevant;
- optional vs required relationships are distinguished;
- external-system boundaries are visible;
- sensitive-data assumptions are marked.

Fail if navigation labels are standing in for domain understanding.

## Gate E — Evidence Challenge Ready
Before requirements are accepted.

Must be true:
- unresolved high-risk assumptions are listed;
- available technical/regulatory/reference evidence has been inspected where relevant;
- direct research availability is stated;
- if no client/user access exists, the project explicitly adopts evidence-constrained mode.

Fail if secondary research is being described as direct user validation.

## Gate F — Requirements Grounding Ready
Before POC scope/design.

Must be true for every accepted P0 requirement:
- source/claim or valid derivation exists;
- origin is explicit/derived/provisional;
- one obligation only;
- rationale exists;
- assumption dependencies are visible;
- fit criterion is observable;
- verification method exists;
- contradictions are resolved or explicitly carried as risk.

Fail if:
- generic SaaS behavior became a requirement without evidence;
- competitor feature became a requirement;
- citation does not actually support the statement;
- technical capability was invented;
- vague terms have no measurable/observable meaning.

## Gate G — POC Scope Ready
Before detailed design.

Must be true:
- primary hypothesis and learning goal are explicit;
- critical scenario exists;
- in/out scope exists;
- requirements included in the slice are known;
- mocked vs real behavior is declared;
- the POC states what it cannot validate.

Fail if scope is merely “build a portal/dashboard” or success means only polish.

## Gate H — Flow Ready
Before high-fidelity/coded work.

Must be true:
- current-state friction is understood or labeled source-derived;
- future-state hypothesis exists;
- IA supports accepted tasks/domain concepts;
- 1–3 critical task flows exist;
- flows reference relevant requirements;
- important exception/error states are known or explicitly deferred.

Fail if screens exist without task-completion logic.

## Gate I — Prototype / Front-End Ready
Before evaluation.

Must be true:
- critical flow works end to end;
- realistic content/data exists;
- mocked integrations are visible;
- no static data is misrepresented as real-time;
- basic keyboard/accessibility behavior works;
- implementation does not contradict the accepted flow.

Fail if the POC is only a visual walkthrough or implementation shortcuts change the tested hypothesis.

## Gate J — Evaluation Ready
Before claiming results.

Must be true:
- evaluation question is explicit;
- verification methods are linked to requirements;
- direct user validation status is explicit;
- if users are unavailable, inspection/review methods are named;
- findings distinguish evidence from interpretation.

Fail if expert review is called user validation or aesthetic approval is treated as proof of usefulness.

## Gate K — Decision Ready
After evaluation.

Must be true:
- verified requirements are distinguishable from unverified ones;
- validation status is explicit;
- findings are evidence-linked;
- remaining unknowns are visible;
- next decision is Proceed / Iterate / Pivot / Stop.

Fail if claims about product-market/user fit exceed available evidence.

## Gate L — Process Learning Ready
Before changing the canonical process.

Must be true:
- a real POC exposed a recurring process failure/improvement;
- proposed change is reusable across future POCs;
- evidence/example is recorded;
- affected templates/agent rules/evals are identified.

Fail if the change is project-specific or preference-driven.

When Gate L passes, update `PROCESS.md`, affected supporting docs/templates, relevant eval cases and `CHANGELOG.md`.