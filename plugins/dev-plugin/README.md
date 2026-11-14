# dev-plugin

Tatolab's development workflow for Claude Code, shared by tatolab/streamlib, tatolab/tatolab-app
(Tato Studio) and tatolab/main-website (tatolab.com).

Work is tracked in Linear: team Tatolab, issues `TAT-n`, titled `streamlib:`, `studio:` or `site:`.
A shared skill takes what one repository needs, such as its gates, its reviewers and the proof a
change needs, from that repository's `CLAUDE.md` section `## Before you push`.

## What it holds

- **Shared skills**: `file-issue`, `plan-project`, `implement`, `whats-next`, `triage`,
  `diagnose`, `research`, `explore-idea`, `grilling`, `architecture-question`,
  `reconcile-understanding`, `module-design`, `propose-rule`, `hygiene`.
- **streamlib skills**: the plan lifecycle (`align`, `propose-change`, `ship-change`, `pivot`,
  `glossary`, `snapshot-architecture`), live verification (`verify-live`, `verify-audio`), the
  stream verbs (`list-running-streams`, `drive-running-stream`, `inspect-live-graph`,
  `read-live-track`, `capture-stream-evidence`, `stop-running-stream`), `attach-artifact` and
  `gh-stack`.
- **Tato Studio skills**: `verify-app`.
- **Repository rules**, as skills that load when Claude works in the files they cover:
  `streamlib-*` and `studio-*`.
- **Agents**: `streamlib-review-pr`, `streamlib-local-ci-runner`, `rust-craftsmanship-reviewer`,
  `evidence-verifier`, `gpu-vulkan-expert`, `linux-media-expert`, `polyglot-ipc-expert`,
  `studio-review-pr`, `studio-local-ci-runner`, `main-process-craftsmanship-reviewer` and
  `window-craftsmanship-reviewer`.
- **machine-brake hook**: in Tato Studio's repository only, notes a Bash command that acts on the owner's real machine, and asks
  before one that publishes. `scripts/machine-brake` edits its config. The defaults are in
  `hooks/machine-brake.json`, and `~/.claude/machine-brake.json` or a project's
  `.claude/machine-brake.local.json` override them.

## Setup

`attach-artifact` needs the Infisical CLI signed in and `wrangler`. The machine-brake hook needs
`jq`, and stays silent without it.
