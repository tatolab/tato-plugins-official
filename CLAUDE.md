# tato-plugins-official

Tatolab's Claude Code plugin marketplace. `.claude-plugin/marketplace.json` lists the plugins, and
each one lives in `plugins/<name>/` in the layout https://code.claude.com/docs/en/plugins-reference
describes.

- **Work is tracked in Linear**, never in GitHub issues: team Tatolab, issues `TAT-n`.
- **One copy of everything.** A skill or agent exists once. Something only one repository needs
  carries that repository's prefix (`streamlib-`, `studio-`, `site-`). What a shared skill needs
  from a repository lives in that repository's `CLAUDE.md` section `## Before you push`, never in
  the skill.
- **Paths inside the plugin** are written `${CLAUDE_PLUGIN_ROOT}/…` in skills, agents and hooks.
  Repository paths stay relative to the repository a session works in.
- **Guards note or ask; they never deny.** A hook never returns `deny` and never exits 2.
- **A new agent** states the knowledge it captures that can't be derived from the code, why the
  existing agents don't cover it, and its model tier: `opus` for implementation and reasoning,
  `sonnet` for mechanical steps, never `fable`.
- **Bump `version`** in the plugin's `plugin.json` on every change that reaches users, so an
  installed copy updates.
- **Before you push**, run what README.md's "Working on this repository" lists. PR titles are
  conventional commits (`type(scope): summary`).
