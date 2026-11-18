# OWNER CONFIRMATION REGISTER — 2026-11-18

**Status:** OWNER_RESPONSES_RECORDED / FOLLOW_UP_DESIGN_AND_LEGAL_REVIEW_PENDING  
**Decision source:** joint owner response submitted in the Yvenist project conversation on 2026-11-18.  
**Owners:** Keven and Rafael.  
**Purpose:** track what the owners have decided, what remains a proposal, and what still requires evidence or specialist review.

> This register supersedes the unanswered-status snapshot in the initial audit. The dated decision record is the detailed source of truth: `00_GOVERNANCE_AND_PROJECT_CONTROL/OWNER_DECISION_RECORD_2026-11-18.md`. Do not keep treating PM-20–PM-26, the brand confirmations or the Product Creation Framework as unanswered. Do not promote proposals in the commercial/operations documents to approved policy.

## 1. Confirmed owner decisions

| ID | Decision | Status |
|---|---|---|
| GOV-01 | Strategic and commercial decisions require approval from both owners. Technical and operational decisions follow designated responsible people; the names/areas will be assigned later. | CONFIRMED — detailed RACI still pending |
| GOV-02 | The Product Creation Framework v0.1 is approved as the official working basis. | APPROVED_AS_OFFICIAL_WORKING_BASELINE |
| DES-01 | Primary brand color is `#FF5637`; this supersedes the earlier `#FF6B00` decision. | CONFIRMED — Figma/token migration pending |
| DES-02 | The three-screen hybrid direction is approved. | CONFIRMED |
| DES-03 | Plus Jakarta Sans is the canonical typeface. | CONFIRMED |
| DES-04 | Keep Material Icons and approve the current mapping, subject to future changes. | CONFIRMED — mapping is revisable |
| DES-05 | No existing app-icon concept is selected; create new explorations. | CONFIRMED |
| DES-06 | The existing foundation-token base is approved as a baseline and may be improved with Claude/ChatGPT support. | APPROVED_BASELINE / ITERATIVE_REFINEMENT |
| DES-07 | The number shown on venue/supplier cards means customer ratings. | CONFIRMED — review eligibility/calculation still requires specification |
| DES-08 | Motion and performance evaluation should be a mandatory approval gate where practicable. | CONFIRMED_AS_DESIGN_QUALITY_GATE |
| PM-20 | Supplier-defined fixed prices vary by event/party type; the Party Maker total updates as items are added/removed; one event request is submitted and each supplier receives its own alert/sub-request. | CONFIRMED — pricing matrix and partial-confirmation rules need specification |
| PM-21 | Date and guest count are required when the selected category or supplier requires them. | CONFIRMED — conditional requiredness matrix needed |
| PM-22 | An event with no items is deleted after a warning to the consumer. | CONFIRMED — recovery/undo interaction still needs UX decision |
| PM-23 | The consumer does not need to accept a supplier-created quote as a separate step. Each supplier confirms whether it can fulfil the requested service on the requested date. | CONFIRMED — define price-change and partial-availability exceptions |
| PM-24 | Consumer and supplier identities are visible to each other from the beginning. | CONFIRMED |
| PM-25 | Each category has its own configuration form. | CONFIRMED |
| PM-26 | A supplier can create kits/bundles and also offer independent/separate services or items. | CONFIRMED |
| PAY-01 | Payment and contracting capabilities are part of the MVP and must be designed and implemented in the Blueprint. | CONFIRMED_SCOPE |
| FLOW-01 | In the Direction page, layer 11 / item 3, V1 becomes the confirmation for an immediate order whose payment has completed; V2 remains the confirmation for a quote/request submitted from Party Maker. | CONFIRMED — Figma frame update/reconciliation pending |
| FLOW-02 | Immediate purchases (e.g. a snack kit) need a conventional cart/checkout path separate from Party Maker event composition. | CONFIRMED_NEED / visual solution to be designed |
| BIZ-01 | Revenue streams: commission on completed bookings/transactions; paid priority placement in contextual Explore results; a consumer subscription may be introduced later with benefits to be designed. | CONFIRMED_DIRECTION |
| BIZ-02 | Supplier commission is percentage-based on the contracted value. | CONFIRMED_DIRECTION — rate, calculation base and payout rules remain open |
| SCOPE-01 | All capabilities listed in the prior MVP scope question are intended to be included in the MVP scope. | CONFIRMED_SCOPE_INTENT — sequence into deliverable slices; do not silently remove capabilities |
| ENV-01 | Rafael's development environment is Windows native; Claude Code is used via terminal. | CONFIRMED |
| ENV-02 | Local repository path is not yet known; two Claude sessions are only probable; Figma version history has not yet been inspected by the owners. | OPEN / TO VERIFY |

## 2. Design and Figma reconciliation

The current human decision for the primary color is `#FF5637`, not the older `#FF6B00`. Existing Figma content and token samples may still contain the older color; treat those as stale source material pending controlled migration, not as a reason to override the new decision.

The currently approved hybrid direction, typeface, Material Icons mapping, rating meaning and V1/V2 confirmation semantics must be reconciled with the latest human-authored Figma state. Preserve any edits the owners make during the ongoing design flow. Before changing frames or tokens, inspect the current live file and capture a dated snapshot; do not restore an earlier version or overwrite intervening owner edits.

Figma file: `Yvenist_v0`, key `G2QX9NnDe8gJOnTrFUw1jH`. Version history is still unverified; the owners report they have not tried to inspect it.

## 3. Open specification work — not owner-decision blockers

- Supplier price matrix: how event type, guest count, quantity, date, add-ons and regional differences affect the fixed listing price.
- Aggregated event request: supplier-specific sub-orders, partial acceptance/decline, expiry, replacement and consolidated payment.
- Conditional date/guest requirements by category and supplier.
- Empty-event warning: wording, destructive confirmation, immediate undo and recovery window.
- Customer-rating system: who can review, when a review becomes eligible, rating aggregation, moderation, verified-purchase indicator and empty state.
- Immediate cart: fulfilment method (delivery, pickup or service redemption), inventory/availability, taxes/fees, order tracking and returns.
- Subscription benefits, paid-placement disclosure and ad inventory rules.
- Detailed MVP feature sequencing and acceptance criteria.
- Named accountable people for technical and operational domains; exact local repo path and actual two-session pilot.

## 4. Commercial, operational, legal and financial review

`MARKETPLACE_COMMERCIAL_AND_OPERATING_MODEL_PROPOSAL_2026-11-18.md` contains proposals for commissions, cancellations, refunds, no-shows, disputes, supplier SLAs, service fulfilment and payment settlement. These are NOT yet policy approvals.

Before real transactions, obtain Brazilian legal, accounting/tax, privacy and payment-provider review. In particular, review consumer cancellation/withdrawal rights, supplier contract terms, payment split/settlement, chargebacks, refunds and any proposed cancellation consequences.

## 5. Source and authority rule

For every decision, retain its exact wording, approving owners, date, rationale, affected flows/data/policies, evidence, implementation impact and review trigger. Strategic and commercial decisions require both owners. Technical/operational decisions are approved by the assigned accountable person once the RACI is named. Do not infer approval from a mockup, source code, payment-provider capability or AI recommendation.
