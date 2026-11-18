# Source Register — Yvenist

**Blueprint baseline:** `1.0.0` (approved architecture)
**Addendum:** project-source registration `0.1`
**Status:** `REGISTERED_BY_OWNER / ACCESS_NOT_YET_AUDITED`
**Last updated:** 2026-11-17

## 1. Purpose

This register identifies the project's declared primary sources and defines what each source can and cannot prove. Registering a URL does not mean that Claude has authenticated access, inspected its contents, or verified that the material is current.

## 2. Declared primary sources

| Source ID | Source | Canonical location | Declared role | Access / verification status |
|---|---|---|---|---|
| `SRC-GH-001` | Yvenist GitHub repository | https://github.com/KevenSanchesG/Yvenist | Existing code repository, Git history, branches, project files and technical implementation evidence | `USER_DECLARED_OFFICIAL / ACCESS_NOT_YET_VERIFIED` |
| `SRC-FIG-001` | Yvenist Figma design file (`Yvenist_v0`) | https://www.figma.com/design/G2QX9NnDe8gJOnTrFUw1jH/Yvenist_v0?t=0u2P7rgPxMKQ5kxX-1 | Design artifact, pages, frames, components, visual decisions and historical design versions | `USER_DECLARED_OFFICIAL / ACCESS_NOT_YET_VERIFIED` |
| `SRC-BP-001` | Yvenist Project Blueprint | This repository/workspace | Governance, approved architecture, project context, source mapping and future specifications | `CONTROLLED_BY_BLUEPRINT_RELEASE` |

## 3. Source authority by domain

Authority is domain-specific; there is no universal rule that the newest file or latest commit automatically wins.

| Domain / question | Primary evidence | Boundary |
|---|---|---|
| What code and technical structure exist now? | GitHub repository at the inspected commit/branch, plus local working-tree evidence | Code is evidence of implementation, not proof that the feature is strategically approved or commercially correct. |
| What was designed in Figma? | Figma file and individually identified version IDs | A frame is evidence of design intent at that point in history, not proof that the design was implemented or approved. |
| Which design direction is currently approved? | Human-approved decision record and the document declared as owner for that decision | Figma recency alone does not establish approval. |
| What business rules are approved? | Approved domain specification and decision log | Do not infer commercial rules from visual labels, mock data or code behavior alone. |
| What did an earlier iteration contain? | Figma version history, Git history, archived documents and dated evidence | Historical material is not an active requirement unless explicitly reinstated. |
| What should be developed next? | Approved product strategy, MVP scope, roadmap and current human decisions | Do not derive priorities solely from issue order, code presence or Figma page order. |

## 4. GitHub source handling

**Declared repository:** `https://github.com/KevenSanchesG/Yvenist`

At integration time, Claude must:

1. Inspect the selected local folder before taking action: confirm whether `.git` exists, run read-only status and remote checks, identify current branch, commit and uncommitted/untracked changes.
2. Compare the configured `origin` (and other remotes, if present) with the declared URL. Record the result; do not silently replace a remote.
3. If the folder is not a Git working copy, do not run `git init` or add a remote automatically. Present the options—use the existing clone, clone the declared repository into a separate destination, or obtain a different target path—and request human authorization before changing the workspace.
4. Preserve the repository's existing commit history, branches, tags, remotes, ignored files and uncommitted work. Never force-push, reset, clean, rebase destructively or overwrite the existing project as a shortcut.
5. Record the exact commit SHA and branch used for every audit or integration report. Distinguish committed state from the local working tree.
6. Treat repository access as unverified until a permitted read succeeds. A public URL or user-provided link does not grant credentials or access to private content.

The `.git` directory is Git's repository metadata directory, not an ordinary document to copy into a ZIP. The existing remote repository must be connected through the normal Git clone/fetch workflow after inspection and authorization.

## 5. Figma source handling and historical versions

**Declared file:** `Yvenist_v0`  
**File key:** `G2QX9NnDe8gJOnTrFUw1jH`  
**User-provided URL:** https://www.figma.com/design/G2QX9NnDe8gJOnTrFUw1jH/Yvenist_v0?t=0u2P7rgPxMKQ5kxX-1

At integration/audit time, Claude must:

1. Confirm that the authorized Figma account can open the file and determine the available access role. If access fails, request the owner to grant access; do not attempt to bypass permissions.
2. Start with read-only inspection: file metadata, page inventory, frame inventory, components, variables/styles where available, links/annotations and current version metadata.
3. Inspect the version history before interpreting earlier work as current. Preserve each relevant version ID, timestamp, author and description as returned by Figma; do not invent missing metadata.
4. When using the Figma REST API, validate current documentation and scopes. The version-history endpoint is `GET /v1/files/:key/versions` and requires `file_versions:read`; retrieving file content requires the applicable `file_content:read` permission. Use a specific version ID when reading a historical snapshot.
5. Build a Figma history ledger that maps relevant version IDs to the pages/frames and design decisions observed. Compare historical iterations only when the underlying evidence is accessible.
6. Reconcile Figma findings with approved decisions, the GitHub implementation snapshot and existing documentation. Record conflicts rather than selecting a winner based only on recency.
7. Do not edit, restore, rename, duplicate, publish, move or delete the original Figma file, pages, components or versions during the audit. Any write operation requires a separate explicit human authorization.
8. Treat screenshots, mock data, labels and comments as design evidence; do not treat them automatically as implemented business rules, verified availability, prices or backend capability.

Official Figma API references:
- Version history: https://developers.figma.com/docs/rest-api/version-history-endpoints/
- File content and version parameter: https://developers.figma.com/docs/rest-api/file-endpoints/
- REST API overview: https://developers.figma.com/docs/rest-api/

## 6. Acquisition and audit status

| Check | Status | Required evidence to close |
|---|---|---|
| GitHub URL registered by project owner | `DONE` | This source register and user's explicit declaration |
| GitHub repository access and visibility tested | `PENDING` | Successful authenticated/read-only access report |
| Git working copy and remotes inspected | `PENDING` | Local `git status`, remotes, branch and commit report |
| Figma URL and file key registered | `DONE` | This source register and user's explicit declaration |
| Figma access and role verified | `PENDING` | Successful file open/API/MCP inspection report |
| Relevant Figma historical versions inventoried | `PENDING` | Version ledger containing exact IDs and metadata |
| GitHub/Figma/approved decisions reconciled | `PENDING` | Cross-source audit and documented conflicts/resolutions |

## 7. Rules for updating this register

- Add a source only with its owner, purpose, authority domain, access conditions and verification status.
- Record the inspected branch/commit, Figma version ID, access date and tool/method in each audit report.
- Never store passwords, access tokens, private keys or personal credentials in this file.
- Keep user-provided links intact; add normalized links only as additional references, not as replacements.
- If a source changes, is superseded or loses access, preserve its historical record and update status rather than silently deleting it.
