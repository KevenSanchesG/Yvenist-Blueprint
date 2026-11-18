# PRODUCT CREATION FRAMEWORK

**Blueprint architecture:** 1.0.0 — APPROVED_AS_WORKING_ARCHITECTURE  
**Document version:** 0.1  
**Status:** PROPOSAL / HUMAN_REVIEW_REQUIRED  
**Document owner:** UNASSIGNED  
**Applies to:** Yvenist company, marketplace, products, services, internal tools and digital surfaces  
**Last updated:** 2026-11-18

---

## 1. Purpose

This framework defines how Yvenist identifies opportunities, understands problems, decides what to create, designs and validates solutions, delivers them, launches them and improves or retires them.

It applies to more than software features. A Yvenist initiative may be a business capability, marketplace policy, supplier operation, consumer journey, digital product, internal tool, brand experience, physical-service process, integration or improvement to an existing capability.

The framework prevents a common failure mode: treating a request, screen, idea or technical possibility as if it were already a validated product requirement. The team must understand the user and business problem, identify the operational system behind the experience, establish evidence and decision authority, and only then commit to a solution and delivery scope.

The process is iterative, risk-based and proportionate. It is not a mandatory bureaucracy in which every small correction requires a complete discovery project. The depth of evidence, documentation, review and approval must match the initiative's impact, uncertainty, cost, reversibility and risk.

## 2. Relationship with the Blueprint and existing project

This document owns the product creation method. It does not replace:

- the Blueprint architecture and domain-specific owner documents;
- the decision authority and RACI model;
- the source register and project source acquisition protocol;
- the existing Yvenist repository Knowledge Base in docs/;
- approved ADRs, product decisions or human approvals;
- specialist review for legal, tax, accounting, privacy, accessibility or security matters.

The Blueprint is a planning and governance layer. The existing application repository is an implementation and engineering evidence source with its own documentation system. During integration, the two must be mapped and reconciled; the Blueprint must not overwrite or duplicate the existing Knowledge Base indiscriminately.

### 2.1. Rule for conflicts between implementation and approved intent

Use the source that is authoritative for the question being answered:

| Question | Authoritative evidence |
|---|---|
| What is implemented at a specific point in time? | Code, tests, CI and Git history at an identified commit/branch; local working-tree evidence where relevant |
| What should the product or business do? | Human-approved decision record and its owner specification |
| What was designed? | Figma page/frame and exact version, with approval status identified separately |
| What was researched or observed? | Research artifact with method, date, sample/context and limitations |
| What is planned but not delivered? | Approved roadmap or initiative decision, not code presence or a mock screen |

If implementation differs from an approved decision, document an implementation gap. Do not silently rewrite the approved decision to match the code. If code reveals that an approved decision is infeasible or unsafe, present the evidence and options to the accountable human. Equally, do not describe a proposal as implemented just because it appears in Figma or a specification.

This rule is the reconciliation policy for the Blueprint and the existing repository. It does not silently modify the target repository's current CLAUDE.md; that change belongs to a later, reviewed integration plan.

## 3. Product creation principles

1. **Start from an outcome and a real problem.** Do not begin with a screen, feature list, technology or competitor imitation.
2. **Understand the whole service.** Consider discovery, decision, preparation, transaction or commitment, fulfillment, support and aftercare where they apply.
3. **Design for all affected actors.** A marketplace feature may affect consumers, suppliers, partners, delivery/fulfillment participants, administrators and support teams.
4. **Evidence before certainty.** Label observations, verified facts, assumptions, hypotheses, proposals and decisions distinctly.
5. **Validate the riskiest assumption early.** Prefer a cheap experiment or prototype over a large implementation based on an untested belief.
6. **Separate desirability, viability, feasibility and operability.** A useful interface is not necessarily a sustainable business or a service the operation can fulfill.
7. **Protect trust.** Be explicit about price, estimate, quote, availability, commitment, responsibility, cancellation, privacy and what the platform does or does not guarantee.
8. **Build end-to-end value.** Prefer a small, complete user outcome over isolated screens that cannot complete a meaningful task.
9. **Keep scope intentional.** Every requirement must have a reason, a user or operational beneficiary, and a release classification.
10. **Measure outcomes, not output volume.** Number of screens, tickets or commits is not proof of product value.
11. **Preserve existing assets and history.** Inspect before restructuring; propose migration before moving or deleting.
12. **Human accountability remains explicit.** AI can research, draft, model, code and test within authorization; it cannot assume company authority or approve high-impact decisions.

## 4. Initiative model and required classification

An **initiative** is any bounded effort intended to create, change, validate or retire a product, service, policy, system or operational capability.

Each initiative must have, at minimum:

- unique ID and descriptive title;
- requesting person or source;
- problem/opportunity and affected actor(s);
- expected outcome and why it matters;
- evidence available and evidence gaps;
- assumptions and hypotheses;
- scope and explicit non-goals;
- dependencies, constraints and risks;
- accountable human decision-maker, or UNASSIGNED;
- delivery owner, or UNASSIGNED;
- current phase, status and next gate;
- acceptance criteria and success measures proportionate to risk.

Classify work before prioritization:

| Class | Meaning | Typical treatment |
|---|---|---|
| NEW_PRODUCT_OR_SERVICE | New user-facing or operational capability | Full lifecycle, adapted to risk |
| PRODUCT_IMPROVEMENT | Change to an existing capability | Focused discovery and impact analysis |
| BUSINESS_OR_MARKETPLACE_POLICY | Commercial, trust, eligibility or operating rule | Human approval; legal/financial review where applicable |
| TECHNICAL_ENABLER | Infrastructure, architecture, reliability, security or developer capability | Link to supported product/operational outcomes |
| EXPERIMENT | Time-bounded test of a hypothesis | Define learning question, exposure, stop rule and decision |
| DEFECT_OR_INCIDENT | Regression, failure, security or service interruption | Incident/quality process; do not force through product discovery |
| MAINTENANCE_OR_COMPLIANCE | Required upkeep or obligation | Track source, obligation, owner and completion evidence |

Also classify release scope using the Blueprint's master taxonomy: MVP, POST_MVP, FUTURE_VISION, OUT_OF_SCOPE or TO_VALIDATE. Never invent local synonyms for these labels.

## 5. Lifecycle and decision gates

The phases below form a learning and delivery loop, not a one-way waterfall. A phase may be shortened, repeated or skipped for a low-risk change when the reason is recorded. A gate is a decision point, not a status badge.

### Phase 0 — Intake and triage

**Question:** What is being requested, by whom, and what outcome might it serve?

**Work:**
- capture the request without assuming the proposed solution is correct;
- identify the affected user, supplier, operational team or system;
- classify the initiative;
- check for an existing owner document, decision, issue, known problem or duplicate initiative;
- identify urgency, impact, reversibility and whether this is actually an incident or defect;
- choose an initial investigation depth.

**Minimum output:** initiative record with problem statement, request origin, classification, initial scope, known evidence, risks, owner/authority and next action.

**Gate 0 — Triage:** accept for discovery, combine with existing work, defer, reject with reason, or route to incident/maintenance handling. No product promise is created by accepting an idea for discovery.

### Phase 1 — Problem discovery

**Question:** Do we understand the problem, the people affected and the context well enough to explore solutions?

**Work:**
- review existing documentation, analytics, support records, operational evidence, prior research and known issues;
- identify user groups and their goals, constraints, workarounds and decision context;
- map the current journey from beginning to end, including offline steps and third parties;
- observe or interview real users when the evidence gap justifies it;
- distinguish what users say, what they do, what the system records and what the team infers;
- examine accessibility, assisted-use needs, device/network constraints, geography, language and other relevant context;
- inspect policy, legal, privacy, security, commercial and technical constraints without pretending to provide specialist advice;
- identify existing alternatives and the cost of leaving the problem unsolved.

**Minimum outputs:** problem statement; actor/context map; current-state journey or process; evidence log; assumptions and open questions; constraints and risk list; initial outcome hypothesis.

**Gate 1 — Problem understood:** proceed when the problem, affected actors, context and material uncertainties are clear enough to test a solution direction. Otherwise continue research, narrow the problem, or stop. Do not build the production solution during discovery merely to make progress visible.

### Phase 2 — Opportunity and concept validation

**Question:** Is there a credible opportunity, and which solution direction deserves further investment?

**Work:**
- frame multiple solution options, including process or policy changes that may not require software;
- state hypotheses in testable form: target actor, expected behavior/outcome, proposed intervention and evidence that would support or refute it;
- evaluate desirability, business viability, technical feasibility, operational feasibility and trust/safety implications;
- identify marketplace network effects and dependencies where relevant, including both demand and supply;
- prototype or test the riskiest assumptions using the cheapest method capable of producing useful evidence;
- define experiment duration/sample/selection method and limitations; do not claim representativeness from convenience samples;
- estimate effort, cost, opportunity cost and failure impact as ranges where precision is unavailable.

**Minimum outputs:** concept options; prioritized hypotheses; experiment/prototype evidence; viability and feasibility notes; recommendation with alternatives; explicit unresolved decisions.

**Gate 2 — Opportunity decision:** proceed to product definition, run another experiment, pivot, defer or stop. A positive usability reaction alone does not establish willingness to pay, supplier capacity or unit economics.

### Phase 3 — Product strategy and definition

**Question:** What outcome will be delivered, for whom, and what is deliberately excluded?

**Work:**
- define target actor(s), use context and job/outcome;
- state value proposition and the relationship to Yvenist's strategy;
- define the smallest coherent scope that can deliver and support the promised outcome;
- set measurable outcome indicators and baseline plans;
- specify business rules, eligibility, roles, permissions, states, exceptions and policy dependencies;
- distinguish mandatory requirements from hypotheses and options;
- define content/information requirements, accessibility expectations and user support;
- map dependencies across marketplace participants, systems and operations;
- record release classification and explicit non-goals.

**Minimum outputs:** product brief; outcome and metric tree; scope/non-scope; prioritized requirements; domain/business rule inventory; actor permissions; open decision log; acceptance criteria.

**Gate 3 — Product intent approved:** accountable human approves the problem, intended outcome, commercial/policy choices and scope. If the relevant authority is UNASSIGNED, keep the decision open and do not present it as approved.

### Phase 4 — Service, UX and interaction design

**Question:** Can each relevant actor understand and complete the intended service journey?

**Work:**
- map the proposed end-to-end service, frontstage and backstage;
- design information architecture, navigation, task flows and state transitions;
- cover loading, empty, validation, error, unavailable, permission, pending, success and recovery states as relevant;
- prototype key journeys before committing to detailed UI;
- test comprehension, usability and accessibility with representative participants where possible;
- define content, terminology, disclosures, price presentation and expectation management;
- specify responsive/device behavior and design-system reuse;
- identify manual operations and support work required behind the interface.

**Minimum outputs:** future-state service blueprint/journey; flows; wireframes or interactive prototype; screen/state inventory; content rules; accessibility review notes; test findings; design decision record.

**Gate 4 — Experience validated:** critical tasks are understandable and feasible; material usability/accessibility risks are addressed or explicitly accepted by the responsible human. Figma frames are design evidence, not proof of implementation or approval unless linked to a decision.

### Phase 5 — Technical and operational solution design

**Question:** Can Yvenist reliably, securely and sustainably deliver and operate the intended service?

**Work:**
- inspect the current codebase, architecture, data model, integrations and test strategy at a known commit and, when available, the local working tree;
- map each requirement to existing capability, extension, new component or unresolved dependency;
- identify data ownership, lifecycle, retention, access, minimization and privacy impact;
- design API contracts, domain boundaries, state transitions, migrations and compatibility;
- assess threat scenarios, abuse, fraud, access control, auditability and sensitive data;
- plan monitoring, support, incident handling, supplier onboarding/operations and fulfillment;
- assess performance, reliability, accessibility, maintainability, deployment and rollback;
- estimate delivery in slices and document meaningful alternatives and trade-offs.

**Minimum outputs:** technical approach/ADR where needed; domain and data changes; API/integration contracts; security/privacy risk notes; operational readiness plan; test strategy; dependency map; delivery plan and rollback approach.

**Gate 5 — Ready to build:** architecture and operations are sufficiently understood; critical dependencies have owners; risky changes have review and rollback plans; human approvals exist for relevant policy and data decisions.

### Phase 6 — Build and integrate

**Question:** Can we implement the smallest complete slice while preserving product, technical and operational coherence?

**Work:**
- create tasks tied to approved requirements and acceptance criteria;
- work on a named branch and protect the local working tree;
- implement domain rules before or with dependent UI;
- maintain parity between clients, APIs and other rule-enforcing systems;
- create/update automated tests and migrations as required;
- keep secrets out of source, logs, prompts and documentation;
- update product, technical, operational and legal/privacy documentation when behavior or data use changes;
- integrate in reviewable increments and keep the main branch protected.

**Minimum outputs:** working code or operational artifact; tests; migration and deployment notes; updated documentation; reviewable commits/PR; unresolved issues list.

**Gate 6 — Implementation complete:** acceptance criteria are met and evidence is attached. A merged commit alone is not evidence that the end-to-end service works.

### Phase 7 — Verification, pilot and release readiness

**Question:** Is the complete service safe and useful enough for the intended release population?

**Work:**
- execute unit, integration, end-to-end, regression, accessibility, security and performance checks proportionate to risk;
- test the complete journey across user roles, system boundaries and operational handoffs;
- verify pricing, disclosures, permissions, state transitions, failure/retry paths and data handling;
- conduct a controlled pilot or beta when uncertainty or impact warrants it;
- define support coverage, supplier/customer communication, monitoring, incident contacts and rollback;
- compare observed results against hypotheses and success measures;
- document known issues and accepted risks transparently.

**Minimum outputs:** test report; pilot findings; release checklist; known limitations; support/monitoring plan; rollback plan; go/no-go recommendation.

**Gate 7 — Release approval:** the relevant human authorities approve launch scope, risk acceptance, legal/policy content and operational readiness. Claude cannot approve launch or accept company risk.

### Phase 8 — Launch and operate

**Question:** Can the promised service be delivered consistently in the real environment?

**Work:**
- release through the approved deployment/store/channel process;
- validate production configuration, access, monitoring, backups and recovery;
- observe actual user and supplier behavior;
- monitor service health, support demand, marketplace health and unexpected harms;
- coordinate incident response, communications and remediation;
- compare outcomes with the baseline and report material deviations.

**Minimum outputs:** release record; deployment/version evidence; operational handover; metrics dashboard or reporting plan; incidents and improvement backlog.

**Gate 8 — Operational acceptance:** the service has an identified owner, support path, monitoring and recovery plan. A launch announcement is not operational acceptance.

### Phase 9 — Learn, improve or retire

**Question:** What did real usage teach us, and should this capability change, expand, remain, or be retired?

**Work:**
- review user outcomes, conversion and retention where applicable, supplier participation, service quality, costs and technical health;
- segment results rather than hide disparities in aggregate metrics;
- compare evidence with original hypotheses and assumptions;
- prioritize improvements, debt, operational changes and new discovery;
- reassess dependencies, standards, APIs, legal obligations and risk;
- plan migration, communication, data handling and support before retirement.

**Minimum outputs:** outcome review; updated assumptions and decisions; next-iteration priorities; retirement plan when relevant.

**Gate 9 — Continue/change/retire:** record the decision and its evidence. Preserve prior versions and explain material changes.

## 6. Marketplace-specific completeness check

For initiatives that touch the marketplace, check both sides of the market and the service that connects them.

### Demand side
- discovery, comparison, confidence and decision-making;
- event planning and configuration;
- price clarity, estimates, quotes and confirmation;
- expectation setting, changes, cancellation and support.

### Supply side
- supplier acquisition, verification and onboarding;
- listing creation, quality, pricing and terms;
- capacity, availability and response expectations;
- quote handling, fulfillment, changes, cancellations and disputes;
- supplier tools, education and support.

### Platform and operations
- search/catalog quality and moderation;
- eligibility, identity, permissions and trust signals;
- matching, recommendations and their explanations;
- payments, fees, refunds and reconciliation only when actually in scope;
- administration, support, incident response and audit trails;
- privacy, retention, fraud/abuse and regulatory obligations;
- geographic density, supply coverage and operational capacity.

Do not assume every marketplace concept is already active in Yvenist. Each capability must be classified against actual implementation, approved intent and release scope.

### 6.1. Yvenist Party Maker guardrail

The existing code repository describes Party Maker as an event-composition capability rather than a shopping cart; its current documentation separates an app-calculated estimate from supplier quotes and states that quote acceptance does not itself reserve a date or collect payment. These are current documented implementation/product descriptions, not a blanket approval of every associated business rule.

ADR-019 and the Party Maker known-issues file explicitly identify business choices awaiting owner confirmation, including quote-per-item behavior, event prerequisites, anonymity and configuration fields. The framework therefore requires those choices to remain visibly unresolved until the accountable humans confirm or change them. Do not silently promote them to approved policy when writing new product specifications.

## 7. Evidence, decisions and traceability

Every material initiative must preserve a traceable chain:

**Problem → Evidence → Hypothesis → Decision → Requirement → Design → Implementation → Test → Outcome**

Use stable IDs where practical for initiatives, requirements, risks, decisions, research findings and test cases. A document must cite the owner document rather than copy its full rules.

For every important claim, record:
- source ID or direct source reference;
- source version/commit/date;
- method of acquisition;
- what the source actually proves;
- limitations, assumptions and confidence;
- whether the claim is current, historical or superseded.

Use the Blueprint status taxonomy consistently:
- APPROVED: approved by the accountable human;
- PROPOSAL: a recommendation awaiting approval;
- ASSUMPTION: an unverified belief being used provisionally;
- UNVERIFIED: not yet checked;
- BACKEND_DEPENDENCY: depends on an unconfirmed capability or change;
- SUPERSEDED: replaced, with history retained;
- REJECTED: formally rejected with rationale.

A completed document, code commit, passing test or polished Figma frame does not independently confer business approval.

## 8. Prioritization and sequencing

Prioritization must consider:
- user outcome and severity of the problem;
- strategic fit and contribution to the ecosystem;
- evidence strength and uncertainty reduction;
- reach, frequency and affected segments;
- marketplace liquidity or network dependencies, where applicable;
- feasibility, dependencies, cost and opportunity cost;
- operational burden and support readiness;
- legal, privacy, security, trust and reputational risk;
- reversibility and cost of delay.

Do not use a numeric score unless the team has documented the scoring scale, weighting, evidence basis and decision authority. A scoring sheet structures discussion; it does not replace accountable judgment.

Prioritize a complete service outcome over a collection of disconnected surfaces. Do not optimize one side of the marketplace in a way that makes the other side or the operating team unable to fulfill the promise.

## 9. Success measures

Each initiative defines one primary outcome measure and a small supporting set. Select measures that match the intended outcome and can be collected responsibly.

| Family | Example questions |
|---|---|
| User outcome | Can the actor complete the task? How much effort, time or uncertainty remains? |
| Activation and conversion | Do qualified users reach the intended next step? Where do they abandon? |
| Marketplace liquidity | Is relevant supply available for demand in the target geography/category? Are requests answered? |
| Supplier performance | Are suppliers able to respond and fulfill within stated expectations? |
| Trust and safety | What complaints, disputes, fraud signals, cancellations or harmful outcomes occur? |
| Operational efficiency | What manual work, support volume and cost are required per completed outcome? |
| Commercial viability | What revenue, variable cost, contribution and repeat behavior are observed? |
| Technical health | Are reliability, latency, accessibility, defect and recovery objectives met? |

These are examples, not approved Yvenist KPIs or target values. Establish baselines before setting thresholds. Do not collect personal data merely because a metric is convenient; define purpose, minimization, access, retention and aggregation.

## 10. Documentation and artifact rules

Use the existing Blueprint architecture and ownership matrix. Produce artifacts only when they resolve a real need; do not create empty documents to satisfy a checklist.

The minimum product brief for a non-trivial initiative should link to:
1. initiative/problem statement;
2. evidence and discovery findings;
3. outcome hypothesis and measures;
4. user/actor and current/future journeys;
5. scope and non-goals;
6. requirements and business rules;
7. decision records and unresolved questions;
8. UX/design evidence;
9. technical and data approach;
10. operational, risk and support implications;
11. acceptance criteria and test evidence;
12. release and learning plan.

Create specialized owner documents for durable rules, not temporary meeting notes. Keep decisions in the decision log/ADR mechanism; keep current facts in the baseline; keep issues in the issue/known-problem register; keep implementation details in the engineering Knowledge Base.

## 11. Human decision rights and AI collaboration

The decision authority matrix remains the owner of approval roles. Until humans are formally assigned, keep the relevant authority UNASSIGNED.

Claude and other AI tools may, within the requested scope:
- explore options and research sources;
- summarize evidence with provenance and caveats;
- draft briefs, flows, specifications, code and test plans;
- inspect authorized repositories and design files;
- identify conflicts, gaps, risks and dependencies;
- implement bounded work and run authorized checks;
- prepare review-ready decisions and release recommendations.

They must not:
- invent user research, customer feedback, supplier commitments, prices, metrics or test results;
- approve strategy, monetization, commissions, policies, legal terms, risk acceptance or launch;
- treat access permission as business authorization;
- install broad permissions, MCP servers, hooks or credentials without review;
- modify production, original Figma assets or the target repository beyond the explicit scope;
- erase history or silently resolve conflicts between authoritative sources.

Every AI-generated material decision recommendation must identify its evidence, assumptions, alternatives and required human approver.

## 12. Multi-session execution

Parallel work is allowed only when tasks are independently bounded and each has clear file ownership and integration criteria.

Before parallel writing:
- verify the actual Git repository, starting commit, branches and clean/dirty state;
- confirm a separate branch and isolated worktree/path for each writing session;
- assign one writer per file and one coordinator for the integration cycle;
- record task, owner, inputs, expected outputs, dependencies and acceptance criteria in the workstream registry;
- do not parallelize two tasks that change the same source-of-truth file or tightly coupled business rules;
- use cross-session messaging only as an auxiliary text channel; Git commits, handoffs and documents remain durable evidence;
- integrate through reviewable commits and run the relevant checks after integration.

The multi-session addendum 0.3 is approved for an operational pilot, not yet cleared for routine parallel production work. Until the pilot is completed and accepted, use the documented pilot constraints or serialize writes.

## 13. Definition of Ready and Definition of Done

### Definition of Ready

An initiative or delivery slice is ready when:
- the problem/outcome is understood to the required depth;
- source documents and current implementation have been checked where relevant;
- scope, non-goals and acceptance criteria are explicit;
- policy and business decisions are approved or clearly marked as blockers;
- dependencies and risks have owners;
- design/technical/operational inputs are sufficient for the task;
- the target repository, branch and write permissions are known;
- the responsible human and review route are known.

### Definition of Done

A delivery slice is done when:
- the agreed acceptance criteria pass;
- relevant tests and quality checks have evidence;
- UX/content/accessibility and operational impacts are considered;
- documentation and decision records are updated;
- known limitations and follow-up work are recorded;
- the change is reviewed and integrated through the agreed Git process;
- release/production claims match what was actually deployed and verified.

Done for documentation, code, pilot and production are distinct states. Never use one as a substitute for another.

## 14. Exceptions and proportionality

A small text correction, low-risk visual adjustment or bounded maintenance task may use an expedited path. The person doing the work must record:
- why the full lifecycle was unnecessary;
- what was checked;
- expected impact and reversibility;
- relevant review/test evidence;
- whether any product, policy, data or security decision changed.

Incidents, security vulnerabilities, legal deadlines and service outages follow the appropriate response process first. Product discovery may follow after containment.

An exception must not bypass explicit human approval for material business, legal, financial, privacy, security or launch decisions.

## 15. Framework maintenance

This document changes only through a reviewed update that:
- identifies the reason and affected phases/gates;
- preserves prior decisions and migration notes;
- checks consistency with architecture, ownership and decision authority;
- updates the Blueprint changelog and progress record;
- receives human approval before its status changes from PROPOSAL to APPROVED.

Future work should create or refine the detailed templates and owner documents referenced here, without copying this framework into each domain.

## 16. Reference baseline

The framework uses these external references as supporting practice, not as binding regulation or a claim that Yvenist is a government service:

- [GOV.UK Service Manual](https://www.gov.uk/service-manual) — user research, design, agile delivery, measurement, technology and service operation.
- [How the discovery phase works](https://www.gov.uk/service-manual/agile-delivery/how-the-discovery-phase-works) — problem framing, user context, constraints, evidence and discovery exit.
- [Core principles of agile](https://www.gov.uk/service-manual/agile-delivery/core-principles-agile) — user needs, iterative delivery, learning and continuous improvement.
- [Governance principles for agile service delivery](https://www.gov.uk/service-manual/agile-delivery/governance-principles-for-agile-service-delivery) — proportionate control, timely human decisions, outcomes and value.

References accessed on 2026-11-18. Recheck external guidance when materially revising this framework.
