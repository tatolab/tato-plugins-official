# Tatolab plugins

The Claude Code plugin marketplace for Tatolab. It holds the agent customizations that used to
live in each repository's `.claude/` folder: skills, subagents, hooks and their scripts.

## Install

```
claude plugin marketplace add tatolab/tato-plugins-official
claude plugin install dev-plugin@tato-plugins-official
```

In a Tatolab repository you don't need either command. Its `.claude/settings.json` lists this
marketplace and enables `dev-plugin`, so Claude Code offers to install both when you trust the
folder.

## Plugins

- **dev-plugin**: how Tatolab builds software. It covers the Linear-tracked issue lifecycle
  (`file-issue`, `plan-project`, `implement`, `whats-next`, `triage`), design and debugging skills,
  streamlib's plan lifecycle and live verification, Tato Studio's app verification, the
  repository rules as skills (`streamlib-*`, `studio-*`), the reviewers and domain experts, and
  the machine-brake hook. See [its README](plugins/dev-plugin/README.md).

## Working on this repository

Check every change before you push:

```
claude plugin validate --strict .
claude plugin validate --strict plugins/dev-plugin
for t in plugins/dev-plugin/scripts/tests/*.sh; do bash "$t" || exit 1; done
```

CI runs the same checks on every pull request.
