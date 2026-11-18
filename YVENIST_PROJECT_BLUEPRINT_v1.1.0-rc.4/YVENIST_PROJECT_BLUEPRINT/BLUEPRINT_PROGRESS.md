# Blueprint Progress

**Architecture baseline:** 1.0.0 — APPROVED_AS_WORKING_ARCHITECTURE  
**Imported source package:** 1.1.0-rc.4  
**Working branch:** main (the preparation branch is retained as history)  
**Phase 1:** CLOSED_WITH_SCOPED_PENDENCIES  
**Multi-session addendum:** 0.3 — APPROVED_FOR_PILOT / OPERATIONAL_PILOT_PENDING  
**Product Creation Framework:** 0.1 — APPROVED_AS_OFFICIAL_WORKING_BASELINE  
**Owner response register:** 2026-11-18 — JOINT_OWNER_RESPONSES_RECORDED

## Completed in Phase 1

- Architecture baseline 1.0.0 and decision BP-ARCH-001 remain approved.
- Structural and governance inventory completed; progressive documentation and 24 numbered domain areas retained.
- Read-only access to the private GitHub source verified through connected GitHub integration.
- Target repository main inspected at 3abfa925cbdcd9aba0f7685bcfb6ee0aecf5baa3.
- Partial target repository tree and Knowledge Base inspected; existing CLAUDE.md, rules, Skill, ADRs and project docs identified for preservation and mapping.
- Historical CI run 37149780621 verified: all five jobs succeeded on the inspected 2026-10-03 commit.
- Source authority policy clarified: code/tests/CI establish implementation facts; approved human decisions establish approved intent; conflicts are tracked, not silently overwritten.
- Source register, acquisition protocol and current-state baseline updated with exact access limitations and owner decisions.
- Multi-session addendum 0.3 approved for pilot; actual Desktop pilot remains pending.
- Product Creation Framework v0.1 approved by both owners as the official working basis.
- Joint owner responses recorded for brand/design, Party Maker decisions PM-20–PM-26, MVP scope, monetization direction, governance and development environment.
- Follow-up design documents created for owner decisions, Party Maker/checkout flows, commercial/operating model proposals and visual-asset/motion pipeline.

## Confirmed product/design direction

- Primary brand color: #FF5637; the previous #FF6B00 decision is superseded.
- Hybrid three-screen direction approved; Plus Jakarta Sans selected.
- Material Icons/current mapping approved, with future revisions allowed.
- App icon needs new explorations.
- Existing design foundation tokens accepted as a baseline, with iterative refinement supported by Claude/ChatGPT.
- Ratings on listing cards represent customer ratings.
- Motion/performance testing is intended to be a mandatory design approval gate where practicable.
- Immediate paid-order confirmation is V1; Party Maker quote/request confirmation is V2.
- Party Maker is a multi-supplier event request with supplier-specific sub-orders and confirmation; separate immediate purchase cart/checkout is required.
- Payment and contracting, plus all capabilities enumerated in the MVP scope discussion, are intended to be MVP scope.

## Scoped pending gates

- Reconcile new owner decisions with the latest live Figma file while preserving ongoing owner edits; update color, token roles, icon exploration and V1/V2 confirmation semantics. Figma version history is still unverified.
- Refine design tokens for contrast, dark/light themes, states, density, motion and accessibility.
- Define the category/supplier price matrix, concrete partial-acceptance/dependency rules and conditional date/guest requirements.
- Design the empty-event delete warning and recovery/undo behavior.
- Turn the documented immediate-purchase cart/checkout into design and implementation slices.
- Specify customer-rating eligibility, aggregation, moderation and verified-review rules.
- COM-01 (taxa progressiva) e COM-02 (base comissionável/descontos) aprovadas conjuntamente como regras comerciais internas em 2026-11-18; permanecem pendentes COM-03 (alocação da taxa PSP), COM-04 (reembolso parcial) e demais decisões de pagamento, SLA, cancelamento, conclusão e repasse.
- Obtain legal/accounting/privacy/payment-provider review before live transactions.
- Assign technical/operational RACI owners and qualified specialist reviewers.
- Inspect local project folder, Git remotes, branch, HEAD and working-tree state on Rafael's computer.
- Execute the real two-session Claude Code/Desktop pilot; current use is Windows native + terminal, but local paths and session behavior are not yet verified.
- Validate and package a new release only after the full diff, docs, config examples and package integrity checks pass.

## Next phase

Continue Phase 2 by closing COM-03/COM-04 and the remaining transaction decisions, validating the payment provider and converting the approved commercial base plus transaction state model into prioritized implementation slices. Preserve the owners' ongoing Figma flow changes as live design input, and sequence MVP delivery into complete vertical slices without silently dropping approved scope.


## Commercial model and transaction lifecycle — active work

- Expanded the commercial/operating model proposal to v0.2 with commission calculation, sponsored placements, future subscription, supplier onboarding, multi-supplier request, payment/split, settlement, contracts, cancellations, no-shows, disputes and legal/accounting/PSP gates.
- Added `ORDER_CONTRACT_PAYMENT_STATE_MACHINE_2026-11-18.md` with aggregate boundaries, state machines, event names, financial invariants and Claude Code acceptance criteria.
- Added `COMMERCIAL_POLICY_APPROVAL_SHEET_2026-11-18.md` so Keven and Rafael can decide remaining commercial parameters together.
- COM-01 is now recorded as jointly approved working business policy: 3% Founding Partner rate for 12 months after the first completed order; transition to 5% only after category/area expansion gate; 10% only after maturity gate and joint review. Notice/acceptance safeguards and local cohort rules are documented below.
- `main` now contains the previously prepared 27-commit phase-1 work; this update continues directly on `main`.


## Local launch and COM-01 — joint decisions (2026-11-18)

- COM-01 progressive commission and Founding Partner program recorded as jointly approved business rule: 3% for 12 months from first completed transaction; 5% after category/area expansion gate; 10% after maturity gate and joint review.
- Transition requires 60 calendar days' advance notice, reminders at 30 and 7 days, explicit supplier acceptance, prospective-only application and no retroactive change.
- Local pilot: Campo Grande / Zona Oeste, with Campo Grande as initial demand nucleus and geographic enablement based on actual provider service coverage.
- First supply cohort target: 20 distinct active Founding Partners across four families, target five per family: venues, buffet/food, decoration/rental, confectionery/sweets/party kits.
- Created local market launch plan and updated commission policy with measurement definitions, internal phase gates, supplier safeguards and Claude Code constraints.
- Production collection remains blocked pending COM-03/COM-04 and remaining transaction decisions, legal/accounting/PSP review and payment sandbox validation.


## COM-02 — base comissionável e descontos (2026-11-18)

- Keven e Rafael aprovaram conjuntamente a COM-02 v1.0 como regra comercial interna.
- A comissão é calculada por fornecedor/subpedido sobre a remuneração efetivamente devida ao fornecedor pela parte concluída, antes da comissão Yvenist e da taxa PSP.
- Descontos suportados pelo fornecedor reduzem a base; parcelas promocionais financiadas pela plataforma/parceiro só preservam a remuneração quando efetivamente compensadas ao fornecedor; campanhas cofinanciadas devem registrar as parcelas.
- Repasse genuíno e documentado a terceiro independente fica separado; entrega, montagem e serviços próprios do fornecedor integram sua remuneração quando contratados.
- Tributos não são excluídos automaticamente. A taxa PSP segue COM-03; detalhes de reembolso/cancelamento seguem COM-04.
- Criado `23_INTEGRATION_AND_HANDOFF/COMMISSIONABLE_BASE_AND_DISCOUNT_POLICY_COM-02_2026-11-18.md`; proposta comercial v0.5, máquina de estados, folha de aprovação, registro dos sócios, changelog, README, progresso e manifesto atualizados.
- Cobrança em produção continua bloqueada até revisão jurídica/contábil, definição COM-03/COM-04 e homologação do PSP.
