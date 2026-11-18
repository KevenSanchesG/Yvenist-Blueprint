# BLUEPRINT RELEASE MANIFEST

**Architecture baseline:** 1.0.0 — APPROVED_AS_WORKING_ARCHITECTURE  
**Imported source package:** 1.1.0-rc.4  
**Working branch:** main (preparation branch retained as history)  
**Working delta status:** PHASE_1_CLOSED_WITH_SCOPED_PENDENCIES  
**Product Creation Framework:** 0.1 — APPROVED_AS_OFFICIAL_WORKING_BASELINE  
**Owner decisions:** joint responses recorded 2026-11-18; COM-01 and local pilot plan approved as working business rules; COM-02/COM-03 and other transaction policies remain pending.

## Version identity

- Architecture baseline 1.0.0 is the approved governing structure.
- Folder/package path YVENIST_PROJECT_BLUEPRINT_v1.1.0-rc.4 identifies the imported rc.4 source package.
- Phase 1 closure, owner decision records and new proposals are committed on main. This does not mean a newly built or signed ZIP release exists.
- Multi-session protocol 0.3 is approved for pilot; routine operational use still requires pilot evidence and acceptance.
- Product Creation Framework v0.1 is approved by both owners as the official working basis.
- Strategic and commercial decisions require both owners; technical/operational approval follows designated accountable owners.

## New/updated deliverables in main

- 00_GOVERNANCE_AND_PROJECT_CONTROL/PRODUCT_CREATION_FRAMEWORK.md — now approved as the official working basis.
- 00_GOVERNANCE_AND_PROJECT_CONTROL/OWNER_CONFIRMATION_REGISTER_2026-11-18.md — updated from open questions to the owners' response status and remaining follow-up work.
- 00_GOVERNANCE_AND_PROJECT_CONTROL/OWNER_DECISION_RECORD_2026-11-18.md — complete dated human decision record.
- 23_INTEGRATION_AND_HANDOFF/CUSTOMER_FLOWS_AND_PARTY_MAKER_RULES_2026-11-18.md — supplier sub-orders, Party Maker, immediate cart/checkout and confirmation-screen logic.
- 23_INTEGRATION_AND_HANDOFF/MARKETPLACE_COMMERCIAL_AND_OPERATING_MODEL_PROPOSAL_2026-11-18.md — proposed commission, promotion, cancellation, refunds, fulfillment, disputes and payment handling; not yet approved policy.
- 23_INTEGRATION_AND_HANDOFF/VISUAL_ASSET_AND_MOTION_PIPELINE_2026-11-18.md — recommended creative/animation tooling and performance approval gate.
- 23_INTEGRATION_AND_HANDOFF/PROJECT_SOURCE_AUDIT_REPORT_2026-11-18.md — dated remote GitHub audit and Figma/local limitations.
- YVENIST/CURRENT_STATE_BASELINE.md — partial remote baseline, now with dated owner-response supplement.
- Updated source register, acquisition protocol, progress and release manifest.

## Design and product decision notes

- Primary color decision is now #FF5637; older #FF6B00 samples in Figma must be migrated deliberately.
- The approved hybrid direction, Plus Jakarta Sans and current Material Icons mapping are confirmed; the icon mapping remains revisable.
- App icon requires new explorations; no current concept is approved.
- Existing design tokens are an approved baseline but require iteration, contrast checks and semantic token mapping.
- In the design's layer 11 / item 3, V1 is immediate order confirmation after payment, while V2 is Party Maker quote/request confirmation.
- Owner edits made during the ongoing design flow must be preserved. The current live Figma structure should be re-read before editing; version history remains unverified.
- No Figma file, target app code or local working tree was modified by this documentation update.

## Local launch and commercial policy additions — 2026-11-18

- `23_INTEGRATION_AND_HANDOFF/LOCAL_MARKET_LAUNCH_PLAN_CAMPO_GRANDE_ZONA_OESTE_2026-11-18.md` — approved working plan for 20 active founding suppliers, four priority category families and Campo Grande / Zona Oeste launch.
- `23_INTEGRATION_AND_HANDOFF/COMMISSION_POLICY_AND_FOUNDING_PARTNER_LAUNCH_2026-11-18.md` — COM-01 v0.2, jointly approved as business policy: 3% for 12 months after first completed transaction, 5% after expansion gates, 10% after maturity gates; 60-day notice and express acceptance.
- `23_INTEGRATION_AND_HANDOFF/COMMERCIAL_POLICY_APPROVAL_SHEET_2026-11-18.md` — COM-01 marked jointly approved; other commercial/payment items remain pending.

COM-01 approval does not authorize production charges. COM-02 commissionable base, COM-03 PSP fee allocation, legal/accounting review and PSP sandbox remain launch gates.

## Package safety

- .mcp.json.example contains no configured servers or credentials.
- .claude/settings.json is not provided as an active configuration.
- No secrets or production credentials are intentionally included.
- Root CLAUDE.md applies only to this Blueprint workspace and must not be copied automatically to the target repository.
- Target Knowledge Base and Claude configuration must be mapped and preserved during integration.

## Validation required before packaging

1. Review the complete branch diff.
2. Confirm internal links and paths.
3. Validate Markdown and JSON/config examples.
4. Check release identity, folder name, manifest and changelog.
5. Run ZIP integrity and duplicate-path checks after packaging.
6. Preserve local environment and Figma version-history limitations as explicit open evidence.
7. Obtain human approval for commercial/operating policy; these documents are proposals only.


## Commercial and transaction specification update — 2026-11-18

The following documents are now in main:
- `23_INTEGRATION_AND_HANDOFF/MARKETPLACE_COMMERCIAL_AND_OPERATING_MODEL_PROPOSAL_2026-11-18.md` — expanded proposal v0.2.
- `23_INTEGRATION_AND_HANDOFF/ORDER_CONTRACT_PAYMENT_STATE_MACHINE_2026-11-18.md` — proposed technical/domain state machine.
- `23_INTEGRATION_AND_HANDOFF/COMMERCIAL_POLICY_APPROVAL_SHEET_2026-11-18.md` — decisions requiring both owners.

These are specifications and recommendations. The commission rate, commissionable base, PSP fee allocation, event payment schedule, temporary supplier hold, deadlines, final cancellation rules, payout trigger and sponsored-placement pricing are not approved yet.

The PSP integration must be selected only after validating real multi-receiver split support, KYC/OAuth, partial refund, chargeback, settlement and reporting for Brazil. Do not treat a 1:1 split product as proof of 1:N availability.
