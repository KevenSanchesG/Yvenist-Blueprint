# OWNER DECISION RECORD — 2026-11-18

**Decision authority:** Keven and Rafael jointly for strategic/commercial decisions.  
**Evidence type:** human owner response recorded in the Yvenist project conversation on 2026-11-18.  
**Status:** owner decisions recorded; implementation and design-file reconciliation pending.

## 1. Brand and design

| ID | Decision | Owner status | Follow-up |
|---|---|---|---|
| BRAND-01 | Primary brand color is `#FF5637`. It replaces the earlier `#FF6B00` decision. | APPROVED | Migrate semantic color tokens and all current design states; retain old value only in historical notes. |
| DESIGN-01 | The three-screen hybrid direction is approved, including the agreed V1/V2 composition described in the Figma direction work. | APPROVED | Check every artboard/state against the latest live owner-edited flow. |
| DESIGN-02 | Plus Jakarta Sans is the only canonical type family. | APPROVED | Align Figma text styles and Flutter theme/assets. |
| DESIGN-03 | Keep Material Icons and approve the current icon-to-glyph mapping. Future revision is allowed. | APPROVED, REVISABLE | Store the mapping as a versioned token/component reference rather than hard-coding separate choices per screen. |
| DESIGN-04 | Create new app-icon explorations; none of the existing concepts has been selected. | APPROVED_DIRECTION | Explore concepts from the brand strategy; check small-size legibility, store icon conventions and trademark risk before selection. |
| DESIGN-05 | The existing design-token base is approved, but should be refined with support from Claude and ChatGPT. | APPROVED_BASELINE / ITERATION_REQUIRED | Audit contrast, semantic roles, dark/light parity, states, density, spacing, elevation, typography and motion tokens before final design sign-off. |
| DESIGN-06 | A score shown on venue/supplier cards means customer rating. | APPROVED | Define review eligibility, aggregation, count, moderation, verified-transaction badge and empty/loading states. |
| DESIGN-07 | Animation and performance validation should be an approval gate when practicable. | APPROVED_QUALITY_GATE | Select a physical low-end reference device and document tests. Recommended reference: Samsung Galaxy A17 5G, 4 GB RAM / 128 GB storage (Brazilian variant), with a release-build test protocol. |

### Accessibility note for the new primary color

The new coral `#FF5637` must be treated as a brand fill, not automatically as a readable foreground/text color for every surface. Its contrast against white is approximately 3.16:1, while dark `#1A1208` against it is approximately 5.85:1. Therefore small white text on this fill should not be the default; prefer a dark label on coral or a darker accessible brand shade for white-label buttons. Recalculate contrast whenever the exact token pair changes.

## 2. Party Maker and order rules

| ID | Owner decision | Follow-up required |
|---|---|---|
| PM-20 | Each item/package has a supplier-defined fixed price that can vary by event/party type. The consumer sees the running total as items are added or removed. One event request is submitted, and each supplier receives its own alert. | Design a single event request containing supplier-specific sub-orders. Define price variables (event type, quantity, guest bands, date, optional extras), price snapshot, response states, partial acceptance and expiry. |
| PM-21 | Event date and guest count are required when the selected category or supplier requires them. | Create a requirement matrix, ideally derived from catalog configuration rather than hard-coded UI conditions. Ask once, progressively, and reuse the data throughout the flow. |
| PM-22 | A party/event with no items must be deleted after showing a warning. | Design the warning, destructive action, immediate undo and a safe recovery mechanism. An empty active event must not persist as a normal event. |
| PM-23 | The consumer does not accept a supplier-generated quote as an additional step. Each supplier is responsible for confirming that it can serve the requested event/date. | Replace the old “consumer accepts quote” state with supplier availability/acceptance. If the supplier proposes a price or scope change, require explicit consumer consent before changing the order total. |
| PM-24 | Both consumer and supplier see each other's identities from the beginning. | Make this visible in the privacy notice and request detail; do not imply anonymity in later documentation. |
| PM-25 | Each category has its own configuration form. | Define category schemas with shared core fields and category-specific fields/requiredness. |
| PM-26 | Suppliers may create kits/bundles and also offer independent/separate services or items. | Model package membership, standalone listings, availability, price and inventory separately. |
| PAY-01 | Payment and contracting are included in the MVP. | Define payment lifecycle, supplier agreement/contract records, split settlement, refunds, chargebacks and proof of fulfillment with a qualified payment provider and legal/accounting review. |

## 3. Distinct purchase and event-planning flows

The owners clarified that not every consumer is planning a whole party. A consumer may need to buy an immediate product or kit, such as a snack kit. Yvenist therefore needs two distinct experiences:

1. **Party Maker:** event composition, multiple suppliers, event-specific item configuration, consolidated request and supplier-specific confirmations.
2. **Immediate purchase:** conventional cart, checkout and paid order flow for a standalone product/kit/service that can be purchased without creating an event.

The cart is not to be repurposed as Party Maker. Shared infrastructure (catalog, price calculation, order/payment services, notifications and support) may be reused, but the user journeys and order types must remain clear.

### Direction-page layer 11 / item 3 — Confirmation

- **V1:** confirmation after an immediate order has been paid successfully. This is a purchase/order-success state, not “quote requested”.
- **V2:** confirmation that a Party Maker quote/request has been submitted. Suppliers still need to respond to their own sub-orders.

The exact current owner-edited Figma frames must be checked before implementation. Keep changes made by Keven and Rafael during the ongoing flow; this decision record does not authorize reverting or overwriting them.

## 4. Business model direction

| ID | Owner direction | Status |
|---|---|---|
| BIZ-01 | Commission on completed contracting/transactions. | APPROVED_DIRECTION |
| BIZ-02 | Paid priority exposure in contextual Explore results shown after a consumer creates an event. | APPROVED_DIRECTION — placement must be visibly disclosed as sponsored/paid. |
| BIZ-03 | A consumer subscription may be introduced in the future, with benefits still to be designed. | FUTURE_DIRECTION — not a launch commitment or a defined benefit list. |
| BIZ-04 | Commission is a percentage of the contracted value. | APPROVED_DIRECTION — rate, calculation base, payment-processing fee and payout timing remain open. |

A detailed commercial model is in `23_INTEGRATION_AND_HANDOFF/MARKETPLACE_COMMERCIAL_AND_OPERATING_MODEL_PROPOSAL_2026-11-18.md`. The proposed initial rate and policies are advisory, not approved business terms.

## 5. MVP scope

The owners state that all capabilities listed in the earlier MVP scope question should be included in the MVP scope: payments, chat, notifications, reviews, availability calendar, listing photos, detail pages, additional categories, event address, help center and the other previously listed capabilities.

This is a scope-intent decision, not permission to implement everything as one unsequenced release. The Blueprint must break the agreed scope into dependency-ordered vertical slices, provide acceptance criteria and show critical path/cost/risk transparently. Do not silently drop listed scope; any change requires owner approval.

## 6. Governance and working environment

- Strategic and commercial decisions require both owners' approval.
- Technical and operational decisions follow designated responsible people. Those assignments will be established later; until then, do not infer technical/operational authority from who happens to implement a task.
- Rafael works on Windows native and uses Claude Code through the terminal.
- The local repository path is still to be confirmed.
- Two simultaneous Claude sessions are probable but not verified by an actual pilot.
- The owners have not yet attempted to inspect Figma version history.
- Product Creation Framework v0.1 is approved as the official working basis.

## 7. Preserve changes in the ongoing flow

All human-authored changes made by Keven and Rafael during the ongoing Figma/design flow must be considered as current design input. Before each design update:
1. read the current live page and relevant frames;
2. capture the current state and list relevant node IDs;
3. reconcile current edits with approved decisions;
4. update only the affected nodes/tokens;
5. check the changed frames visually and in light/dark states;
6. record what changed and why.

Do not restore older versions or rebuild from stale screenshots without explicit owner instruction. Figma version history is currently unverified.


## 8. Commercial model and transaction lifecycle — proposal status

On 2026-11-18, the owners asked to develop the commission model and the complete contracting cycle. This work is documented separately; it does not create new owner approvals for percentages or policies.

- The existing approved direction remains: percentage-based supplier commission on completed contracting; paid priority exposure in contextual Explore; future consumer subscription.
- The 10% pilot commission, commission base, PSP fee allocation, deposit/balance terms, temporary availability hold, supplier response SLAs, cancellation/no-show rules and payout trigger are recommendations awaiting approval by both owners.
- The proposed system uses one EventRequest with SupplierSubOrders, separate immediate CheckoutOrder, PaymentGroup, PaymentIntent, ContractRecord, CommissionEntry, PayoutRecord, RefundRecord and DisputeCase.
- Supplier availability confirmation is distinct from payment and final contract generation. The recommended flow creates a temporary AvailabilityHold, then finalizes contract after the consumer completes the contracting/payment step.
- The owner approval sheet is `23_INTEGRATION_AND_HANDOFF/COMMERCIAL_POLICY_APPROVAL_SHEET_2026-11-18.md`.

No commercial fee or cancellation penalty is approved by this supplement. Both owners must approve the final terms, and specialist review is required before production charges.

### COM-01 — proposta apresentada por Keven em 2026-11-18

Keven solicitou levar para aprovação conjunta o modelo híbrido de comissão progressiva, com taxa de lançamento de 3%: 3% para Parceiros Fundadores na fase de lançamento, 5% na expansão e 10% como taxa-alvo de maturidade. A comissão seria paga pelo fornecedor e incidiria somente sobre subpedido concluído. Esta é uma proposta formalizada para deliberação, **não uma decisão conjunta aprovada**. Rafael ainda precisa aprovar a mesma estrutura ou propor alterações. Ver `23_INTEGRATION_AND_HANDOFF/COMMERCIAL_POLICY_APPROVAL_SHEET_2026-11-18.md` e `COMMISSION_POLICY_AND_FOUNDING_PARTNER_LAUNCH_2026-11-18.md`.
