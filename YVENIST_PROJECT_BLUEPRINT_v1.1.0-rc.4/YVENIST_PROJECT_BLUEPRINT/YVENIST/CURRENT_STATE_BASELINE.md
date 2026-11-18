# YVENIST — Current State Baseline

**Snapshot date:** 2026-11-18  
**Status:** PARTIAL_REMOTE_AND_FIGMA_STRUCTURE_SNAPSHOT / LOCAL_GIT_AND_FIGMA_HISTORY_UNVERIFIED  
**Evidence report:** `23_INTEGRATION_AND_HANDOFF/PROJECT_SOURCE_AUDIT_REPORT_2026-11-18.md`  
**GitHub snapshot:** `main` at `3abfa925cbdcd9aba0f7685bcfb6ee0aecf5baa3`  
**Figma file:** `Yvenist_v0`, key `G2QX9NnDe8gJOnTrFUw1jH`

This is a dated factual snapshot. It is not a roadmap, business approval or statement of production readiness. Remote and local repository evidence must remain distinct.

## 1. Repositories and code

| Item | Observed state | Evidence | Date |
|---|---|---|---|
| Declared remote repository | Read access succeeded through connected GitHub integration | `KevenSanchesG/Yvenist`, `main` | 2026-11-18 |
| Remote HEAD | `3abfa925cbdcd9aba0f7685bcfb6ee0aecf5baa3` | GitHub ref API | 2026-11-18 |
| Commit date | 2026-10-03T19:51:10Z | GitHub commit metadata | 2026-11-18 |
| Recursive tree | 792 entries, not truncated | GitHub recursive tree | 2026-11-18 |
| Flutter application | Present in `lib/` | Repository tree and root docs | 2026-11-18 |
| Backend | Present in `backend/`; root docs identify FastAPI, SQLAlchemy, Alembic and PostgreSQL | Repository tree and README | 2026-11-18 |
| Project Knowledge Base | Present in `docs/` | Repository tree and target `CLAUDE.md` | 2026-11-18 |
| Local project clone | UNVERIFIED | No local filesystem/terminal inspection | — |
| Local branch, remotes and working tree | UNVERIFIED | No local `git status` or remotes inspection | — |

## 2. Product capabilities documented at inspected commit

The root README and Knowledge Base describe catalog/search, accounts, favorites, Party Maker event composition, category-specific item configuration, app-calculated estimate, supplier quote request/response/revision/history, supplier onboarding for venues, administrative review and light/dark themes.

The same documentation marks payments, in-app chat, notifications, written reviews, event addresses, help center, listing photos, availability calendar, listing detail page, two-factor authentication and supplier onboarding beyond venues as unavailable or “Em breve” at that snapshot.

This is a documentation-derived summary, not independent runtime verification. Recheck during local integration.

## 3. Product decisions and unresolved questions

ADR-019 and the Party Maker known-issues document mark PM-20 through PM-26 as awaiting owner confirmation. The vision document identifies monetization as an open question. No approval is inferred from the existing implementation or from Figma screen variants. See `OWNER_CONFIRMATION_REGISTER_2026-11-18.md`.

## 4. CI evidence

GitHub Actions run `37149780621` on `main` commit `3abfa925cbdcd9aba0f7685bcfb6ee0aecf5baa3` completed successfully on 2026-10-03. All five jobs — Flutter, Python/PostgreSQL backend, app/API/PostgreSQL integration, Android and Docker — reported success.

This is historical evidence for that commit only. No tests, builds or CI runs were executed by the 2026-11-18 audit.

Run: https://github.com/KevenSanchesG/Yvenist/actions/runs/37149780621

## 5. Figma design baseline

| Item | Observed state | Evidence | Date |
|---|---|---|---|
| File access | Current file opened read-only through Figma integration | File key `G2QX9NnDe8gJOnTrFUw1jH` | 2026-11-18 |
| Top-level pages | Five: Base · Antigo; Direção; Fundações; Componentes; Telas · Cliente | `get_metadata` | 2026-11-18 |
| Client screen section | Party Maker · começo; 126 first-level frame variants | Page `535:2` | 2026-11-18 |
| Component library page | 81 top-level frame groups | Page `266:2` | 2026-11-18 |
| Design foundations | Working tokens include #FAF7F4, #FFFFFF, #F3EEE9, #FFEDE0, #1E1A16, #5A5249, #716A60, #FF6B00 and #B34500 | Page `210:2` and variables | 2026-11-18 |
| Figma comments | Empty list returned | `get_comments` | 2026-11-18 |
| Subscribed libraries | None added to file | `get_libraries` | 2026-11-18 |
| Version history | UNVERIFIED / NOT RETRIEVED | No version-history action exposed by the available connector in this session | — |
| Approved design details | Mixed: decisions, proposals, inferences and items to confirm coexist on the Direção page | Exact sections described in source audit report | 2026-11-18 |

The Fundações page describes the token set as working values pending confirmation. The four icon concepts in section 15 are marked without approval. The three-screen hybrid in section 14 is labelled approved by Rafael and Keven, but some detailed elements remain inference/confirmation items. Use the owner confirmation register.

## 6. Business and operations

Legal/corporate status, named approval authorities, active suppliers, active regions, pricing, monetization, commissions, payments, customer support and fulfillment operations are not established by this remote code/Figma structure audit. Keep them UNVERIFIED or UNASSIGNED until the appropriate humans and source documents confirm them.

## 7. Claude Code and integrations

| Item | Observed state | Evidence |
|---|---|---|
| Target repository `CLAUDE.md` | Present and read at remote commit | GitHub remote |
| Target `.claude/` | Present | Repository tree |
| Project rules | Seven area rules reported in the inspected tree | Repository tree |
| Project Skill | `atualizar-memoria` exists | Repository tree and docs |
| Installed Claude Desktop/Code version | UNVERIFIED | No access to development computer |
| Owner's live two-session behavior | UNVERIFIED | Desktop pilot not performed |
| Local MCP servers and permissions | UNVERIFIED | No local settings inspection |

## 8. Update protocol

1. Create a dated snapshot with exact source, commit/version and acquisition method.
2. Record remote and local states separately.
3. Cite the smallest path, commit or Figma version that proves each claim.
4. Separate observation, repository documentation, human report and inference.
5. Do not store credentials, tokens, private keys or unnecessary personal data.
6. Preserve prior snapshots where history matters.


## 9. Joint owner decisions received on 2026-11-18

A joint owner response now confirms the following product/design direction: primary brand color `#FF5637` (superseding the former `#FF6B00`); approved three-screen hybrid; Plus Jakarta Sans; Material Icons with the current mapping approved but revisable; no existing app icon selected; design foundation tokens approved as a baseline for iterative refinement; card scores represent customer ratings; and motion/performance review intended as a design approval gate.

Party Maker decisions: supplier-defined fixed prices vary by event/party type; totals update as items are added or removed; one event request is submitted with individual supplier alerts/sub-requests; date and guest count are conditionally required by category/supplier; empty events are deleted after a warning; suppliers confirm availability/fulfilment instead of requiring a consumer quote-acceptance step; identities are visible from the start; forms are category-specific; and suppliers may sell kits/bundles and independent services/items.

Payments and contracting are included in MVP scope. All previously listed functional areas are intended to be in MVP scope, subject to explicit dependency-based sequencing. The owners also clarified that immediate purchases require a standard cart/checkout path distinct from Party Maker.

The owners' live edits during the ongoing Figma flow must be preserved. The live Figma snapshot inspected on this date still includes older `#FF6B00` and earlier V1/V2 confirmation labels in some places; the new owner decisions supersede those historical labels and require a controlled design/token reconciliation. Figma version history remains unverified.

See:
- `00_GOVERNANCE_AND_PROJECT_CONTROL/OWNER_DECISION_RECORD_2026-11-18.md`
- `23_INTEGRATION_AND_HANDOFF/CUSTOMER_FLOWS_AND_PARTY_MAKER_RULES_2026-11-18.md`
- `23_INTEGRATION_AND_HANDOFF/MARKETPLACE_COMMERCIAL_AND_OPERATING_MODEL_PROPOSAL_2026-11-18.md`
- `23_INTEGRATION_AND_HANDOFF/VISUAL_ASSET_AND_MOTION_PIPELINE_2026-11-18.md`

This section records human-reported decisions and does not assert that the Figma file or Flutter application has already been updated.
