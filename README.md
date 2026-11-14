# Tatolab plugins

Tatolab's Claude Code plugin marketplace: the skills, agents, hooks and MCP servers for working in
Tatolab's repositories.

## Install

```
claude plugin marketplace add tatolab/tato-plugins-official
claude plugin install dev-plugin@tato-plugins-official
```

In a Tatolab repository you don't need either command. Its `.claude/settings.json` lists this
marketplace and enables `dev-plugin`, so Claude Code offers to install both when you trust the
folder.

## Plugins

- **dev-plugin**: the common development plugins for working in Tatolab's repositories. See
  [its README](plugins/dev-plugin/README.md); `claude plugin details dev-plugin@tato-plugins-official`
  lists everything it installs.

## Working on this repository

Check every change before you push:

```
claude plugin validate --strict .
claude plugin validate --strict plugins/dev-plugin
for t in plugins/dev-plugin/scripts/tests/*.sh; do bash "$t" || exit 1; done
```

CI runs the same checks on every pull request.
