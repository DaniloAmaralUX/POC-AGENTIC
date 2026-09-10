# POC Decision Gates

These gates prevent downstream work from converting uncertainty into false certainty.

A gate is not bureaucracy. It is a checkpoint asking whether the next phase would increase learning or merely increase output.

## Gate A — Evidence Ready

Before synthesis.

Must be true:
- source material has been read;
- evidence inventory exists;
- source perspectives are identified;
- obvious contradictions are recorded;
- missing source material is visible.

Fail if:
- the agent is relying on snippets while full material exists;
- stakeholder statements are already being treated as user truth;
- the team cannot say what evidence exists.

## Gate B — Problem Ready

Before actors/domain modeling.

Must be true:
- Facts, Assumptions and Open Questions are separated;
- the problem can be explained without proposing UI;
- major unknowns and risks are documented.

Fail if:
- the “problem” is expressed only as a requested feature;
- assumptions dominate the synthesis but are not marked.

## Gate C — Primary Actor Ready

Before future-state and POC scoping.

Must be true:
- primary actor is explicit;
- primary job/task is explicit;
- stakeholder and user are not conflated;
- evidence level behind the actor definition is known.

Fail if:
- persona is invented from demographics;
- multiple incompatible users are being designed for simultaneously without prioritization.

## Gate D — Domain Ready

Before IA.

Must be true:
- core entities exist as a model;
- relationships are explicit;
- optional vs. required relationships are identified where relevant;
- external-system boundaries are visible;
- sensitive data/identity assumptions are marked.

Fail if:
- navigation labels are being used as the domain model;
- a page structure is forcing the data model prematurely.

## Gate E — POC Scope Ready

Before detailed design.

Must be true:
- primary hypothesis is explicit;
- learning goal is explicit;
- critical scenario is explicit;
- in-scope and out-of-scope lists exist;
- success evidence is defined;
- mocked vs. real behavior is declared.

Fail if:
- scope is just “build a portal/dashboard”;
- every stakeholder request is included;
- success means only “looks polished”.

## Gate F — Flow Ready

Before high-fidelity prototype or coded POC.

Must be true:
- current-state friction is understood;
- future-state hypothesis exists;
- IA supports known tasks/domain concepts;
- 1–3 critical task flows exist;
- important exception/error states are known or explicitly deferred.

Fail if:
- screens exist without task completion logic;
- generic SaaS IA was used without evidence.

## Gate G — Prototype Ready

Before usability testing.

Must be true:
- participant can understand the scenario;
- realistic data/content exists;
- critical tasks are actually interactive;
- facilitator does not need to explain how the UI works;
- known mocks do not misrepresent product capability.

Fail if:
- prototype is only a visual walkthrough;
- task completion depends on hidden facilitator instructions.

## Gate H — Front-End Ready

Before claiming the POC is executable/testable.

Must be true:
- critical flow works end to end;
- mocked integrations are identified;
- realistic loading/empty/error states exist where relevant;
- basic keyboard/accessibility behavior works;
- target viewport/context works;
- implementation does not contradict the approved flow.

Fail if:
- UI suggests data is real-time when it is static without disclosure;
- implementation shortcuts materially change the test hypothesis.

## Gate I — Validation Ready

Before running sessions.

Must be true:
- research questions are explicit;
- representative tasks are written;
- participant profile is defined;
- success/failure observations are defined;
- moderator script exists where needed;
- capture method is defined.

Fail if:
- research consists primarily of “Do you like this?”;
- there is no relationship between task and POC hypothesis.

## Gate J — Decision Ready

After validation.

Must be true:
- findings distinguish observation from interpretation;
- severity/impact is justified;
- hypothesis outcome is stated;
- remaining unknowns are visible;
- next decision is explicit: proceed, iterate, pivot or stop.

Fail if:
- design changes are made without connecting them to evidence;
- positive stakeholder reaction is used as a substitute for user validation.

## Gate K — Process Learning Ready

Before changing this repository's canonical process.

Must be true:
- a real POC exposed a recurring process failure or improvement;
- the proposed change is likely reusable across future POCs;
- evidence/example is recorded;
- affected documentation/templates are identified.

Fail if:
- change exists only because one project had a special case;
- the method is being changed based on preference alone.

When Gate K passes, update `PROCESS.md`, affected templates and `CHANGELOG.md`.