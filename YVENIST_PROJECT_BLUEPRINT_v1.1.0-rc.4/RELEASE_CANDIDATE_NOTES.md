# Release Candidate Notes — Yvenist Project Blueprint 1.1.0-rc.4

- Approved base architecture `1.0.0` remains unchanged.
- Source registration includes GitHub `https://github.com/KevenSanchesG/Yvenist` and Figma `Yvenist_v0`; authenticated access remains pending.
- Multi-session protocol is addendum `0.3`, status `PROPOSAL / READY_FOR_DESKTOP_PILOT`.
- Corrected rc.3's mistaken conclusion: current official Claude Code docs explicitly document cross-session messaging.
- Version requirements: Windows native Claude Code `v2.1.234+`; macOS/Linux/WSL 2 `v2.1.224+`; `@session` mentions `v2.1.232+`.
- Native messages are text and auxiliary; they do not transfer files/history, approve permissions, change settings or execute text commands. Git, commits, registry and handoffs remain durable sources.
- Corrected Desktop Worktree rule: the control is off by default and must be enabled before starting each session requiring isolation.
- Two independent Desktop sessions plus messaging are not Agent Teams.
- Temporary Git worktree simulation passed for isolation, separate commits, non-conflicting integration and conflict detection.
- Actual Desktop pilot, installed versions, GitHub authenticated access and Figma authenticated access remain pending.
- See `YVENIST_PROJECT_BLUEPRINT/00_GOVERNANCE_AND_PROJECT_CONTROL/ADDENDUM_1.1.0_RC4_REVIEW_AND_TEST_REPORT.md` and `.../MULTI_SESSION_COLLABORATION/MULTI_SESSION_PILOT_TEST_PLAN.md`.
