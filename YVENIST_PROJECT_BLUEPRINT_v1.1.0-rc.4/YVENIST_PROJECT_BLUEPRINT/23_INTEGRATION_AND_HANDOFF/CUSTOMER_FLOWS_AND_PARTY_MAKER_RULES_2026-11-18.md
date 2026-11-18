# CUSTOMER FLOWS AND PARTY MAKER RULES — 2026-11-18

**Status:** product direction approved by owners; interaction and technical details below are design recommendations until individually accepted.  
**Authority:** owner decisions PM-20–PM-26, PAY-01 and FLOW-01/FLOW-02.

## 1. Two different consumer intentions

Yvenist must support two distinct journeys. Do not make the cart the event composer, and do not force an immediate buyer to create an event.

### A. Plan and compose an event — Party Maker

1. Create an event and enter its basic purpose/type.
2. Discover/add spaces, buffet, decoration, attractions, kits and other categories.
3. Open only the configuration relevant to the chosen category.
4. Ask for date and guest count only when at least one selected category/supplier requires the field; collect it once and reuse it.
5. Show supplier-defined prices and update the event total immediately as the consumer adds, removes or changes quantities.
6. Submit one consolidated event request.
7. Split the request into supplier-specific sub-orders/notifications.
8. Each supplier confirms availability and whether it can fulfil its portion.
9. Show confirmed, declined and pending suppliers clearly; the event is not fully confirmed while required sub-orders remain unresolved.
10. Once the relevant suppliers confirm, collect payment according to the approved payment model and generate a traceable contracting record.
11. Track service preparation, event fulfillment, completion, review and support.

**Important:** the one-button submission is a single consumer action, not one indivisible supplier contract. Each supplier must be able to accept/decline its own sub-order, and the consumer must understand partial availability.

### B. Buy immediately — standalone cart and checkout

Use this for products/kits/services that do not require the customer to compose an event first (example: a kit of salgadinhos).

1. Product/service detail page shows price, what is included, fulfillment mode, availability/lead time, seller and clear terms.
2. Actions: **Comprar agora** and **Adicionar à sacola**.
3. The cart contains only immediate-purchase lines, quantities, selected options, seller groupings, delivery/pickup details, subtotal, clearly disclosed fees/discounts and total.
4. Checkout collects only the necessary fulfillment and payment data.
5. A paid-order confirmation appears only after payment is successfully confirmed by the payment provider.
6. The consumer can follow status, receive messages/notifications, request help and review after fulfillment.

For MVP, support a simple first release of this flow (single-seller cart initially if multi-seller split checkout increases payment/fulfillment risk). Keep the domain model capable of multi-seller orders, but do not introduce cross-seller delivery promises without an operational owner and tested fulfillment design.

## 2. Supplier pricing and total calculation — PM-20

### Confirmed rule

Each listing/item/package has a fixed supplier-defined price for the applicable party/event type. The consumer sees a running total; one event request is submitted and the platform notifies each supplier separately.

### Recommended catalog pricing model

Store a price configuration per listing with:
- price amount and currency;
- applicable event types;
- optional guest-count bands or quantity ranges;
- unit/bundle definition;
- required options and price-affecting add-ons;
- validity start/end and availability window;
- delivery, setup, travel or other separately priced charges where relevant;
- tax/fee treatment confirmed with accounting;
- version/effective date.

Do not silently modify an existing submitted order when a supplier edits a listing later. At submission, store a price snapshot for each line item. If the supplier cannot honour that snapshot, the system should mark the line as requiring resolution; any price increase or scope change must be shown and explicitly approved by the consumer before payment or contract amendment.

### Aggregate request model

Use an EventRequest aggregate with multiple SupplierSubOrders. Each line belongs to a supplier. The aggregate calculates a total, but response, availability and fulfilment are supplier-specific. Keep separate statuses for:
- event request;
- supplier sub-order;
- payment;
- contract;
- fulfilment/completion;
- refund/dispute.

Suggested supplier sub-order states: `draft`, `submitted`, `awaiting_supplier`, `confirmed`, `declined`, `change_required`, `expired`, `cancelled`, `paid/contracted`, `in_fulfilment`, `completed`, `disputed`, `refunded`.

These are a proposed state vocabulary, not a claim that the target code already implements them.

## 3. Date and guest count — PM-21

Represent requiredness as metadata owned by category/listing configuration (for example `requires_event_date` and `requires_guest_count`). The user interface should:
- ask at event creation only for globally useful fields;
- defer category-specific questions until needed;
- reuse previously entered answers;
- explain why a field is needed;
- validate once before submission rather than repeatedly asking on each supplier card.

When a second selected supplier requires a field already collected, reuse the saved value. If selected suppliers require conflicting formats or ranges, explain the constraint and let the consumer resolve it before submitting.

## 4. Empty event — PM-22

Owner rule: an event with no remaining items is deleted after a warning.

Recommended low-friction interaction:
- only show the warning when removal of the last item is about to leave the event empty;
- explain that the event and its selected items will be removed;
- offer a clear destructive action and a non-destructive "keep event / add another item" action;
- after deletion, offer a short-lived **Desfazer** action;
- retain enough safe navigation context to return the consumer to the catalog without restarting unrelated app onboarding.

An empty event must not remain in the active event list. Whether a recoverable "recently deleted" area or a short undo window is used is still an owner UX decision; never silently delete a non-empty event.

## 5. Supplier response replaces consumer quote acceptance — PM-23

Remove the generic consumer step "accept supplier quote" from the default happy path. Supplier confirmation is the decision point for whether the service can be performed on the requested date/terms.

Recommended behaviour:
- each supplier receives its own request notification and has an explicit response action;
- confirm = supplier accepts the requested scope/date/price snapshot;
- decline = supplier cannot fulfil; record reason and notify the consumer;
- partial acceptance is permitted at the event aggregate level;
- no response by the configured deadline expires that supplier sub-order and alerts the consumer;
- if the supplier proposes a different amount, date or scope, the sub-order becomes `change_required`; the consumer must consent to that change before payment/contract amendment.

The last case is not the former quote-acceptance ceremony. It is explicit consent to a material change in what the consumer would buy.

## 6. Identity — PM-24

Both parties see each other's identities from the beginning. Show verified business identity and relevant contact/operational information in context, but only disclose personal data needed for the transaction. Align profile display and privacy notices with Brazilian data-protection review.

## 7. Category forms and supplier packages — PM-25/PM-26

Each category has its own form. Use a shared schema for common fields (description, quantity, date/guest requirements, price, availability, images, seller, terms) plus category-specific configuration.

Suppliers may create:
- **kits/packages:** a named bundle of multiple items/services, priced as a package, with explicit included/excluded contents;
- **standalone listings:** an independent item or service that can be selected separately;
- **optional add-ons:** extras attached to a listing, with clear price and requiredness.

Prevent double-counting when consumers add a package and then add one of its included items separately. Make package contents visible before adding.

## 8. Payment and contract — MVP

Keep the payment lifecycle separate from the order/fulfilment lifecycle. Proposed payment states include `not_required`, `awaiting_payment`, `processing`, `paid`, `failed`, `partially_refunded`, `refunded`, `chargeback`.

For event requests, the recommended order is supplier availability confirmation first, followed by the payment step for the confirmed supplier set. For an immediate purchase, payment occurs at checkout and the paid-order confirmation appears only after successful payment confirmation. The chosen payment provider must support the intended marketplace/sub-order and payout pattern; do not implement a self-managed balance/escrow model without legal, accounting and provider review.

The contract/booking record should preserve what was agreed: seller, consumer, items, price snapshots, dates, address/fulfilment, cancellation terms, accepted changes, payment status, supplier confirmation and audit events.

## 9. Direction page — layer 11, item 3

The owners' updated meaning is:

| Variant | Intended use | When shown |
|---|---|---|
| V1 | Immediate order confirmation after successful payment | After the payment provider confirms a standalone order |
| V2 | Party Maker request/quote submission confirmation | Immediately after the consumer submits the consolidated event request, before supplier responses |

Do not label V1 as "orçamento solicitado". Keep V2's quote/request context distinct from a paid order. Final copy and frame IDs must be reconciled against the latest Figma edits.

## 10. MVP sequencing

All previously listed functional areas are intended to be within MVP scope. Deliver them as dependency-ordered slices rather than a large simultaneous build:
1. identity/catalog/listing/price and availability foundations;
2. Party Maker aggregate and supplier-specific sub-orders;
3. supplier confirmations, notifications and communication;
4. immediate purchase cart, fulfilment and payment;
5. event payment/contracting and split settlement;
6. refund/cancellation/support/dispute handling;
7. customer reviews and moderation;
8. analytics, sponsored Explore and future subscription foundation.

This list is a proposed implementation order; the scope decision itself remains as stated by the owners.


## 11. Contract and payment lifecycle reference

The owner-approved consumer flows are now complemented by the proposed domain specification:
- `ORDER_CONTRACT_PAYMENT_STATE_MACHINE_2026-11-18.md` defines aggregate boundaries, independent states, event transitions, webhooks/idempotency, contracts, commission and payouts.
- `MARKETPLACE_COMMERCIAL_AND_OPERATING_MODEL_PROPOSAL_2026-11-18.md` defines commercial assumptions and operational policy proposals.
- `COMMERCIAL_POLICY_APPROVAL_SHEET_2026-11-18.md` lists the remaining joint owner decisions.

For implementation, keep EventRequest, SupplierSubOrder, PaymentGroup, PaymentIntent and ContractRecord separate. The consumer should experience one consolidated review/checkout, even if the PSP requires payment intents per supplier. Do not equate supplier availability confirmation with payment success or final contract creation.

The 10% pilot commission, event deposit rules, hold duration, supplier SLAs, cancellation windows and payout timing remain proposed pending joint approval. No real payment provider or production policy is authorized by these documents.
