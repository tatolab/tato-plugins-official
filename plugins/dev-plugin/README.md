# dev-plugin

The common development plugins for working in Tatolab's repositories. Install it once and every
Tatolab repository gets the same skills, agents and MCP servers; each repository's
`.claude/settings.json` enables it.

## Install

```
/plugin install dev-plugin --marketplace tatolab/tato-plugins-official
```

## How it fits a repository

- **Shared skills** take what one repository needs, such as its gates, its reviewers and the proof
  a change needs, from that repository's `CLAUDE.md` section `## Before you push`. They hold no
  repository paths.
- **Repository-specific skills and agents** carry the repository's prefix in their name
  (`streamlib-`, `studio-`, `site-`), so one plugin serves every repository without collisions.
- **MCP servers** the skills rely on are declared in `.mcp.json`. Today that is Linear's, where
  Tatolab tracks work; Claude Code asks you to sign in to it on first use.

`claude plugin details dev-plugin@tato-plugins-official` lists every skill, agent and server
it installs.

## Setup

Sign in to Linear when Claude Code prompts. `attach-artifact` needs the Infisical CLI signed in
and `wrangler`.

## Privacy

The plugin stores nothing itself. The Linear MCP server is Linear's service, under
[Linear's privacy policy](https://linear.app/privacy).
