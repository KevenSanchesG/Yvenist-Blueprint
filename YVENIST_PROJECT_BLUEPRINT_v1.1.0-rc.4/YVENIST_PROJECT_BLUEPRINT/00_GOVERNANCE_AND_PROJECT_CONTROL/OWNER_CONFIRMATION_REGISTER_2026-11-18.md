# OWNER CONFIRMATION REGISTER — 2026-11-18

**Status:** OPEN / HUMAN_CONFIRMATION_REQUIRED  
**Authority source:** `00_GOVERNANCE_AND_PROJECT_CONTROL/DECISION_AUTHORITY_AND_RACI.md`  
**Purpose:** consolidate decisions and confirmations required from the human owners. This register does not assign authority or approve proposals by itself.

## 1. Governance and responsibility

| ID | Item requiring confirmation | Current evidence/status | Required human action |
|---|---|---|---|
| GOV-01 | Assign accountable humans for business, product, technology, design/brand, operations and finance | RACI document keeps named people `UNASSIGNED` | Confirm names, domains, individual or joint approval, and escalation route |
| GOV-02 | Assign qualified legal/privacy and security reviewers when needed | No named reviewers recorded | Identify professional reviewers before legal/privacy/security sign-off |
| GOV-03 | Confirm who can approve release, budget, commercial policy and changes to production | No approved authority mapping | Record explicit approval rights; do not infer them from GitHub/Figma access |

## 2. Business and product decisions

| ID | Item | Source evidence | Status / action |
|---|---|---|---|
| BIZ-01 | Yvenist monetization and revenue model | `docs/00-project/vision.md` identifies monetization as an open question; code documentation says no charge is implemented at the inspected revision | Owners must decide the intended revenue model and when it applies; finance/legal review as appropriate |
| PM-20 | Whether supplier quotes are requested and returned per item | ADR-019 / Party Maker known issues | Awaiting owner confirmation |
| PM-21 | Whether requesting a quote requires a future event date and guest count | ADR-019 / PM-21 | Awaiting owner confirmation |
| PM-22 | Whether an event may remain empty and persist after its final item is removed | ADR-019 / PM-22 | Awaiting owner confirmation |
| PM-23 | Meaning of “quote accepted”; whether it remains explicitly non-reserving and non-payment | ADR-019 / PM-23; the inspected docs state no reservation or payment | Confirm exact product/legal meaning and user-facing wording |
| PM-24 | Whether supplier and customer identities remain hidden from each other in the quote flow | ADR-019 / PM-24 | Awaiting owner confirmation; assess trust, support and legal implications |
| PM-25 | Category-specific configuration fields and requiredness | ADR-019 / PM-25 | Confirm the product rules for each category |
| PM-26 | Configuration fields for services supplied by the listing owner | ADR-019 / PM-26 | Confirm which fields apply to each own-vendor service |
| BIZ-02 | Whether and when in-app chat, notifications, payments, reviews, availability and other roadmap capabilities enter scope | Existing repository docs mark several as not implemented / “Em breve” | Prioritize through strategy and roadmap; do not treat Figma screens as proof of implementation |
| BIZ-03 | Supplier commercial terms, cancellation, refunds, disputes, commissions and platform obligations | Not fully settled by the remote code audit | Decide in owner documents with operations, finance and legal input |

## 3. Brand and design confirmations from Figma

Figma file: `Yvenist_v0`, key `G2QX9NnDe8gJOnTrFUw1jH`. The items below are based on the current readable page metadata/text, not a version-history audit.

| ID | Item | What the current Figma evidence says | Required confirmation |
|---|---|---|---|
| DES-01 | Brand orange #FF6B00 | Direção page labels it a decision attributed to Rafael on 2026-10-28; another note still says Keven needs to confirm the orange | Reconcile the contradictory approval notes and record a single joint/authorized brand decision |
| DES-02 | Three-screen hybrid direction | Section 14 “Híbrida aprovada: 3 telas (30/10)” describes approval by Rafael and Keven, while some detailed choices are separately labelled inference / to confirm with Rafael | Confirm the exact accepted scope and create/link a formal decision record |
| DES-03 | App icon | Section 15 contains four explorations A–D and explicitly marks all as “sem aprovação” | Select or reject concepts jointly; perform separate visual and trademark review; no concept is final now |
| DES-04 | Typography | Direction page still records an open Inter versus Plus Jakarta Sans choice; hybrid section says the hybrid uses only Plus Jakarta Sans | Confirm the canonical typeface and reconcile with implemented Flutter assets/tokens |
| DES-05 | Icon library and icon-to-glyph mapping | A note lists icon set/mapping as pending; Components page has an icon family | Confirm the supported icon set and final mapping |
| DES-06 | Rating semantics | Direction page asks what the “nota” on a venue card represents | Define provenance, calculation, display conditions and empty/missing state before real ratings are shown |
| DES-07 | Motion validation hardware | Direction page asks for an entry-level Android device to evaluate motion | Choose device/test profile and accessibility/performance criteria |
| DES-08 | Foundation token status | Fundações page describes token values as working values dated 2026-10-31, with confirmation still pending; tokens include #FAF7F4, #FFFFFF, #F3EEE9, #FFEDE0, #1E1A16, #5A5249, #716A60, #FF6B00 and #B34500 | Confirm which tokens are approved baseline vs proposal and map them to Flutter theme values |
| DES-09 | Client Party Maker screens | Client screens page contains 126 first-level frame variants; some states include “Pago” and “Orçamento aceito” | Confirm which screens/states are current, future, sample-only or deprecated; reconcile with implemented state machine |

## 4. Release and operational blockers recorded in the target repository

The target repository's known-issues document at the inspected commit lists the following release or live-use concerns. This register does not independently validate them beyond the repository documentation:

- KI-01: legal terms are preliminary and need legal review/company details.
- KI-02: privacy policy and account-deletion page lack public URLs.
- KI-03: API is not hosted.
- KI-05: iOS has not been built and requires a Mac/Xcode workflow.
- KI-60: ADR-019 business choices still require owner confirmation.
- KI-61: notifications are absent.
- KI-62: quote acceptance does not reserve a date, create a contract or collect payment; quote response expiry is not implemented.
- KI-63: free-text item/vendor messages may receive personal data.

For each blocker, establish owner, target milestone, acceptance evidence and whether it blocks internal testing, beta, store publication or real transactions.

## 5. Decision capture rule

For every resolved item, create or update the designated owner document and decision record with:
- decision ID and exact wording;
- accountable human(s) and approval date;
- alternatives considered and rationale;
- affected scope, users, policies and systems;
- implementation/documentation impact;
- evidence and reviewer input;
- review date or trigger.

Do not change a status to `APPROVED` merely because a discussion, prototype, implementation or this register exists.
