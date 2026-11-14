---
name: studio-licensing
description: The licensing rules for tatolab/tatolab-app (AGPL-3.0 or commercial). Use when adding a dependency, a font or anything licence-related in tatolab-app.
---

# Licensing

- Tatolab.app is dual-licensed (`LICENSE`): AGPL-3.0-only, or a commercial licence from the
  copyright holder. `LICENSE` covers every file in the repository, so a source file carries no
  licence header of its own. Never suggest another licence for it, never drop the commercial
  option, and never copy its code into `tatolab/streamlib` (GPL-3.0-only).
- The runtime the app bundles is streamlib's and stays GPL-3.0-only; third-party components keep
  their own licences, shadcn's generated components in `packages/tato-app-view-sdk/src/design_system/ui/`
  their MIT form. A new dependency that ships inside the app (an npm package bundled into
  `apps/tato-app/out/renderer/`, a font) is named in the PR body with its licence, so the owner sees what the app
  now redistributes.
- Never modify `LICENSE` without explicit approval.
