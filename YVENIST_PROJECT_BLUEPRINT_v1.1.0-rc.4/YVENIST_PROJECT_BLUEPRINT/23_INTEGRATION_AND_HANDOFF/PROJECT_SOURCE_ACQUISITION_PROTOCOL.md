# Project Source Acquisition Protocol

**Blueprint baseline:** `1.0.0`  
**Addendum:** registered project sources `0.1`  
**Status:** `PROPOSAL / ACCESS_PENDING`

## 1. Declared sources

- **GitHub code repository:** https://github.com/KevenSanchesG/Yvenist (`SRC-GH-001`)
- **Figma design/history file:** https://www.figma.com/design/G2QX9NnDe8gJOnTrFUw1jH/Yvenist_v0?t=0u2P7rgPxMKQ5kxX-1 (`SRC-FIG-001`; key `G2QX9NnDe8gJOnTrFUw1jH`)
- Source authority and status are maintained in `00_GOVERNANCE_AND_PROJECT_CONTROL/SOURCE_REGISTER.md`.

These links were explicitly designated by the project owner. They are registered as intended official sources, but access and contents have not yet been audited by this Blueprint release.

## 2. Acquisition sequence

1. Read `SOURCE_REGISTER.md`, this protocol and the target repository compatibility checklist.
2. Identify the intended project root and inspect it read-only before cloning, initializing Git, changing remotes or copying files.
3. Verify GitHub access and compare the existing remote URL with the declared repository. Record branch, commit SHA and working-tree state.
4. Verify Figma access with the authorized account and identify whether the available route is Figma MCP, REST API or manual read-only inspection.
5. Inventory current source state before historical analysis.
6. Acquire selected historical Figma versions by exact version ID, keeping an evidence ledger.
7. Reconcile source evidence with approved internal decisions and current project implementation.
8. Produce an audit report and a proposed integration plan; request human approval before write operations.

## 3. GitHub: target repository inspection

The GitHub repository is the declared code/history source. It is not, by itself, the source of truth for every product or business decision.

Read-only checks should establish:

- whether the selected folder is already a Git working copy;
- all configured remotes and whether `origin` matches the declared URL;
- current branch, HEAD commit and upstream tracking;
- local modifications, untracked files and ignored files relevant to the work;
- existing project layout, Flutter packages/apps, CI workflows, issue/PR conventions and documentation;
- existing `CLAUDE.md`, `.claude/`, `.mcp.json` and other configuration.

If there is no `.git`, do not create one automatically. The repository already has a declared GitHub URL; ask whether to use an existing clone or clone it into a separately selected destination. Never replace the remote, reset, clean, force-push, rebase destructively or overwrite existing history without explicit authorization.

## 4. Figma: current design and historical design investigation

The Figma file is the declared design source. Audit it read-only.

### Current file

Capture, where accessible:

- file metadata and current version identifier;
- page names and page ordering;
- frames and relevant flows;
- component and component-set inventory;
- variables, styles and libraries accessible to the authorized account;
- comments, annotations and links relevant to decisions;
- access role and limitations.

### Historical versions

1. Retrieve the version list using the current official Figma API documentation. The documented endpoint is `GET /v1/files/:key/versions`; it requires `file_versions:read`.
2. Select versions based on meaningful design milestones, known dates, named releases or user-designated periods. Do not assume every version must be downloaded.
3. Retrieve each selected snapshot using the file endpoint's `version` parameter with the exact version ID; `file_content:read` is required for file content.
4. Record version ID, timestamp, author, description, relevant pages/frames, observations and any missing metadata.
5. Compare old/new designs and distinguish retained, changed, removed, superseded and undecided elements.
6. Map findings to approved decision records and implementation evidence where possible.

Do not restore or modify an old version as part of an audit. A historical version can inspire or explain a design but is not automatically approved for reuse.

## 5. Cross-source reconciliation

Do not use a simplistic global source ranking. Determine which source is authoritative for the specific question:

- **Implementation fact:** inspect GitHub at an exact commit/branch and, when relevant, the local working tree.
- **Design fact:** cite the exact Figma page/frame and version ID.
- **Approved intent or business rule:** use an approved decision record and its owner document.
- **Historical intent:** use archived documents, commit history or Figma version history as historical evidence only.

If GitHub shows a feature that conflicts with an approved product rule, record the implementation discrepancy; do not silently rewrite the rule. If Figma conflicts with current approved design decisions, record the divergence; do not assume the most recent Figma snapshot is approved. Escalate unresolved contradictions to the responsible humans.

## 6. Required outputs

The source-acquisition workstream should deliver:

1. `SOURCE_ACCESS_REPORT.md` — access method, identity/role, access status, date, repository branch/commit and Figma current version.
2. `GITHUB_PROJECT_AUDIT.md` — project structure, existing configurations, code/documentation inventory and risks.
3. `FIGMA_VERSION_LEDGER.md` — relevant version IDs, dates, descriptions, pages/frames and observations.
4. `CROSS_SOURCE_RECONCILIATION.md` — agreements, gaps, contradictions and questions requiring human decisions.
5. `INTEGRATION_PLAN.md` — proposed safe integration steps, paths, backup/rollback and review gates.

If any source is inaccessible, produce a partial report with the exact blocker and requested access. Do not infer its contents.

## 7. Prohibited during acquisition

Without a separate explicit human approval, do not:

- create or replace Git repositories/remotes;
- change branches, reset or rewrite Git history;
- push, merge, delete branches or open/merge PRs;
- edit, restore, duplicate or move the original Figma file;
- add or remove pages, frames, components, libraries or variables;
- change permissions, invite users or alter external services;
- copy secrets or credential files into the Blueprint.

## 8. Official documentation

- GitHub repository declared by owner: https://github.com/KevenSanchesG/Yvenist
- Figma file declared by owner: https://www.figma.com/design/G2QX9NnDe8gJOnTrFUw1jH/Yvenist_v0?t=0u2P7rgPxMKQ5kxX-1
- Figma version-history API: https://developers.figma.com/docs/rest-api/version-history-endpoints/
- Figma file API: https://developers.figma.com/docs/rest-api/file-endpoints/
- Claude Code Desktop: https://code.claude.com/docs/pt/desktop
