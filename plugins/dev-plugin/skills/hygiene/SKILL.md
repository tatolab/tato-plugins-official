---
name: hygiene
description: Sweep the repo for rot an agent might read and obey — rules, skills and comments that contradict the code, references to deleted things, dead rule scopes, stale Linear issues. Use after a large change ships, or when something feels off.
---

# Hygiene

A report. Spotting staleness is mechanical; a finding that is plainly a record (a dead
reference, a mention of a deleted file, a comment the code falsifies) can be fixed in the
same pass, in a PR that says so.

Sweep:

1. **Contradictions with the code.** README claims, comments, rules, skills, agents and
   CLAUDE.md lines that are false against the tree: paths, commands, options, platform or
   CI behaviour. The code wins.
2. **References to deleted things**: removed features, files, skills, workflows or vocabulary,
   anywhere in rules, skills, agents, hooks, comments or memory files.
3. **Dead rules.** Rule `paths:` globs that match nothing, and prose a check now enforces; those
   go to `propose-rule` for deletion.
4. **Stale Linear issues.** Open issues that describe code that has changed, or whose blocking
   issue is Done or Canceled. Summarize only; `triage` does the grooming.

Output one list, ordered by how likely an agent is to read the wrong text and act on it. Each
finding gives the place, the evidence (`file:line` or a quote), and where the fix goes: a PR,
`propose-rule`, `triage`, `file-issue` for another repo, or the owner.
