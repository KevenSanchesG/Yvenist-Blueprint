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
- Obtain joint approval for commercial parameters in the approval sheet: commission base/rate, PSP fee allocation, payment schedule, supplier hold/SLA, cancellation, completion and payout.
- Obtain legal/accounting/privacy/payment-provider review before live transactions.
- Assign technical/operational RACI owners and qualified specialist reviewers.
- Inspect local project folder, Git remotes, branch, HEAD and working-tree state on Rafael's computer.
- Execute the real two-session Claude Code/Desktop pilot; current use is Windows native + terminal, but local paths and session behavior are not yet verified.
- Validate and package a new release only after the full diff, docs, config examples and package integrity checks pass.

## Next phase

Continue Phase 2 by closing the joint commercial approval sheet, validating the payment provider and converting the transaction state model into prioritized implementation slices. Preserve the owners' ongoing Figma flow changes as live design input, and sequence MVP delivery into complete vertical slices without silently dropping approved scope.


## Commercial model and transaction lifecycle — active work

- Expanded the commercial/operating model proposal to v0.2 with commission calculation, sponsored placements, future subscription, supplier onboarding, multi-supplier request, payment/split, settlement, contracts, cancellations, no-shows, disputes and legal/accounting/PSP gates.
- Added `ORDER_CONTRACT_PAYMENT_STATE_MACHINE_2026-11-18.md` with aggregate boundaries, state machines, event names, financial invariants and Claude Code acceptance criteria.
- Added `COMMERCIAL_POLICY_APPROVAL_SHEET_2026-11-18.md` so Keven and Rafael can decide remaining commercial parameters together.
- COM-01 refined into a formal hybrid launch proposal submitted by Keven: 3% Founding Partner launch rate, 5% expansion rate and 10% maturity target; supplier-paid per completed sub-order. Awaiting Rafael's joint approval; thresholds and transition criteria remain open.
- `main` now contains the previously prepared 27-commit phase-1 work; this update continues directly on `main`.
