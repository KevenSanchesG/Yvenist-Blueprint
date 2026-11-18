# Project Source Acquisition Protocol

**Blueprint baseline:** 1.0.0  
**Protocol version:** 0.2  
**Status:** PARTIALLY_EXECUTED / LOCAL_AND_FIGMA_EVIDENCE_PENDING  
**Audit report:** PROJECT_SOURCE_AUDIT_REPORT_2026-11-18.md

## 1. Declared sources and current evidence

- GitHub code repository: https://github.com/KevenSanchesG/Yvenist (SRC-GH-001)
- Figma design/history file: https://www.figma.com/design/G2QX9NnDe8gJOnTrFUw1jH/Yvenist_v0?t=0u2P7rgPxMKQ5kxX-1 (SRC-FIG-001; key G2QX9NnDe8gJOnTrFUw1jH)

GitHub was read successfully through the connected integration on 2026-11-18. Inspected main commit: 3abfa925cbdcd9aba0f7685bcfb6ee0aecf5baa3. This confirms remote read access through that integration only. Local clone and Git state were not inspected. No Figma content or version metadata was retrieved.

## 2. Acquisition sequence

1. Read SOURCE_REGISTER.md, this protocol and the target compatibility checklist.
2. Identify the local project root and inspect it read-only before cloning, initializing Git, changing remotes or copying files.
3. Verify .git, remotes, branch, HEAD, upstream and uncommitted/untracked/ignored state.
4. Compare local HEAD with the intended remote branch; record divergence and preserve user changes.
5. Verify Figma access and role with the authorized account. If file content cannot be read, record the limitation and request a supported route.
6. Inventory current source state before historical analysis.
7. Acquire selected historical Figma versions by exact version ID.
8. Reconcile source evidence with approved decisions and implementation.
9. Produce an audit report and proposed integration plan; obtain human approval before writes.

## 3. GitHub inspection

The GitHub repository is the declared code/history source, not the source of truth for every product or business decision.

Remote inspection should establish branch, commit SHA, repository layout, documentation, rules, CI and Git history. Local integration must additionally establish .git, all remotes, current branch, HEAD, upstream, local modifications, untracked/ignored files, project layout, CI, CLAUDE.md, .claude/ and MCP settings.

If there is no .git, do not create one automatically. Ask whether to use an existing clone or clone into a separately selected destination. Never replace remotes, reset, clean, force-push, rebase destructively or overwrite history without explicit authorization.

## 4. Figma inspection

Audit the Figma file read-only. Capture metadata, access role, current version, pages, frames, components, variables/styles, comments and links when available.

Use current official API documentation. The documented version-history endpoint is GET /v1/files/:key/versions and requires file_versions:read. Reading file content requires applicable file_content:read access. Use exact version IDs for historical snapshots.

Record version ID, timestamp, author, description, relevant page/frame and missing metadata as returned. Do not restore or modify an old version during acquisition.

## 5. Cross-source reconciliation

- Implementation fact: inspect GitHub at an exact commit/branch and the local working tree where relevant.
- Design fact: cite exact Figma page/frame and version ID.
- Approved intent or business rule: use human-approved decision record and owner document.
- Historical intent: use archived documents, commit history or Figma version history as historical evidence only.

If code conflicts with an approved product rule, record the implementation discrepancy; do not silently rewrite the rule. If Figma conflicts with an approved design decision, record the divergence; do not assume the newest snapshot is approved. Escalate unresolved contradictions to the responsible humans.

## 6. Actions prohibited without separate authorization

Do not initialize or replace Git repositories/remotes, force-push, delete or rewrite history, overwrite working files, commit to the target repository, merge branches, modify production, or edit/restore/publish the original Figma file as part of source acquisition.

Read access and write authorization are separate. Approval to audit a source is not approval to modify it.
