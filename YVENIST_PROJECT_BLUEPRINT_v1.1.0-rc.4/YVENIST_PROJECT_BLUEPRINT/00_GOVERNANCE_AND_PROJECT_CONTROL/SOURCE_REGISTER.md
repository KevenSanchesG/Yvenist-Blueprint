# Source Register — Yvenist

**Blueprint baseline:** 1.0.0  
**Working branch:** docs/phase-1-close-2026-11-18  
**Status:** PARTIALLY_VERIFIED / SOURCE_LIMITATIONS_RECORDED  
**Last updated:** 2026-11-18

## 1. Purpose

This register identifies primary sources and states what each can and cannot prove. Registering a URL does not prove access. A successful connector/API read does not prove that a local clone, another user's account or an operating environment has equivalent access.

## 2. Declared primary sources

| Source ID | Source | Canonical location | Declared role | Access / verification status |
|---|---|---|---|---|
| SRC-GH-001 | Yvenist GitHub repository | https://github.com/KevenSanchesG/Yvenist | Code, Git history, branches, project files and implementation evidence | READ_ONLY_ACCESS_VERIFIED_VIA_CONNECTED_GITHUB_INTEGRATION; local clone not audited |
| SRC-FIG-001 | Yvenist Figma design file (Yvenist_v0) | https://www.figma.com/design/G2QX9NnDe8gJOnTrFUw1jH/Yvenist_v0?t=0u2P7rgPxMKQ5kxX-1 | Design pages, frames, components, variables and version history | REGISTERED / CONTENT_NOT_READ / ACCESS_UNVERIFIED |
| SRC-BP-001 | Yvenist Project Blueprint | This repository/workspace | Governance, approved architecture, project context, source mapping and specifications | CONTROLLED_BY_BLUEPRINT_RELEASE |

## 3. Source authority by domain

Authority is domain-specific; the newest file or commit does not automatically win every disagreement.

| Domain / question | Primary evidence | Boundary |
|---|---|---|
| What code and technical structure exist now? | GitHub at an identified commit/branch, tests and CI; local working-tree evidence when relevant | Code is evidence of implementation, not proof that a feature is strategically approved or commercially correct. |
| What was designed in Figma? | Figma file and individually identified version IDs | A frame is evidence of design state at that point in history, not proof of implementation or approval. |
| Which design direction is approved? | Human-approved decision record and its owner document | Figma recency alone does not establish approval. |
| What business rules are approved? | Human-approved decision record and the domain specification it owns | Do not infer final commercial rules from labels, mock data, code behavior or proposals alone. |
| What did an earlier iteration contain? | Figma version history, Git history, archived documents and dated evidence | Historical material is not an active requirement unless explicitly reinstated. |
| What should be developed next? | Approved strategy, MVP scope, roadmap and current human decisions | Do not derive priorities solely from issue order, code presence or Figma page order. |

### 3.1 Conflict resolution

- Code, tests and CI establish what a specified implementation revision does.
- An approved human decision and its owner document establish approved intended behavior.
- If they disagree, record an implementation gap or a decision needing review.
- Do not silently rewrite approved intent to match code, or describe intended behavior as already implemented.
- A source can be authoritative for an implementation fact without having authority to approve business, commercial or legal policy.

## 4. GitHub source handling

Declared repository: https://github.com/KevenSanchesG/Yvenist

Read-only access was verified through the connected GitHub integration on 2026-11-18. Inspected main at commit 3abfa925cbdcd9aba0f7685bcfb6ee0aecf5baa3. This did not inspect a local working copy.

At local integration time, Claude must inspect .git, remotes, branch, HEAD, upstream, uncommitted/untracked/ignored files, compare local and remote state, and preserve all user changes. Do not initialize Git, replace remotes, reset, clean, force-push, rebase destructively or overwrite history without explicit authorization. Connector verification is remote read access only; it does not verify Claude Desktop or local Git credentials.

## 5. Figma source handling

Declared file: Yvenist_v0  
File key: G2QX9NnDe8gJOnTrFUw1jH

No Figma file contents or version metadata were retrieved in the 2026-11-18 audit. This is a limitation of the available reading route, not a conclusion that the owner lacks permission.

When an authorized route is available, inspect metadata, role, current version, pages, frames, components, variables/styles, comments and links read-only. Use the documented GET /v1/files/:key/versions endpoint with file_versions:read; retrieve selected historical snapshots by exact version ID using applicable file_content:read access. Record exact metadata as returned. Do not edit, restore, rename, duplicate, publish, move or delete the original file during audit.

Official references:
- https://developers.figma.com/docs/rest-api/version-history-endpoints/
- https://developers.figma.com/docs/rest-api/file-endpoints/
- https://developers.figma.com/docs/rest-api/

## 6. Acquisition and audit status

| Check | Status | Evidence / next action |
|---|---|---|
| GitHub URL registered | DONE | This register |
| GitHub remote read access | VERIFIED_READ_ONLY | Connector read on 2026-11-18; main at 3abfa92 |
| Git local working copy and remotes | PENDING | Inspect on development computer |
| Target repository documentation snapshot | PARTIAL_DONE | See dated source audit report |
| Figma URL and key registered | DONE | This register |
| Figma content access and role | PENDING | No usable file-reading route in audit session |
| Relevant Figma historical versions | PENDING | Version ledger with exact IDs and metadata required |
| GitHub/Figma/approved decisions reconciled | PARTIAL_PENDING | GitHub snapshot partially reviewed; Figma and local evidence missing |

## 7. Rules for updates

Add a source only with owner, purpose, authority domain, access conditions and verification status. Record exact branch/commit or Figma version, access date and method. Never store passwords, access tokens, private keys or personal credentials. Preserve superseded or inaccessible source history.
