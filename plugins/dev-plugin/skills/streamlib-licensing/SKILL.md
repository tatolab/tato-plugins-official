---
name: streamlib-licensing
description: The licensing rules for tatolab/streamlib (GPL-3.0-only and the vendored exceptions). Use when adding a source file, vendoring code, or touching anything licence-related in streamlib.
---

# Licensing

- StreamLib is GPL-3.0-only. Never suggest another licence for it. A new dependency must be
  GPL-3.0-compatible; `deny.toml` holds the allow list.
- Every new `.rs` file starts with (and every new `.py` file with the same lines after `#`):

  ```rust
  // Copyright (c) 2025 Jonathan Fontanez
  // SPDX-License-Identifier: GPL-3.0-only
  ```

- Vendored third-party trees keep the licence they arrived under. Never add a GPL header to
  one, and never reformat or "improve" those sources — a change to one is a recorded
  patch against its upstream, never a drive-by edit:
  - `vendor/tatolab-vulkanalia`, `-sys` and `-vma` — the vulkanalia fork, Apache-2.0.
- The exception is those paths and nothing else. A vendored tree not listed there, or
  first-party code beside one, still carries the GPL-3.0-only header.
- Never modify `LICENSE` without explicit approval.
