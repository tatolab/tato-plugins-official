---
name: streamlib-engine-doctrine
description: The engine doctrine for tatolab/streamlib: the code is the truth, one core system per concern, prohibited patterns and conventions. Use before designing or changing engine code in streamlib.
---

# Engine doctrine

StreamLib is a game-engine-shaped substrate: one core system per concern, many consumers each.

## The code is the truth; sessions implement

- Code is the only source of truth. Linear issues say what to build. If work needs an
  architecture decision the issue doesn't state, **bring it to the owner** — ask it while you
  keep going on what doesn't depend on it, or build your recommendation and state it as an
  assumption in the PR.
- When the owner changes direction, the old shape is ripped out — no parallel old/new coexistence.
- Scope is what the Linear issue states. Findings outside it go in the PR description as notes,
  not into new issues and not into the diff.

## Structure

- **Search first, extend never parallel.** Before adding any trait / struct / helper / module,
  prove no core system already covers the concern (RHI, `GpuContext`, pubsub, node model).
  Extend the existing one; a parallel abstraction is the default-wrong move.
- **Engine-wide defects get fixed at the engine layer**, never bandaided in the consumer that
  surfaced them.
- **Pattern migrations cover the engine tree only** — runtime, SDK, adapters, engine tests. Consumers are never in a migration's scope: a converted consumer's breakage is filed as
  tracked backlog at that consumer; held pre-pivot consumers lag by design.

Prohibited in library code (tests/examples exempt):
- No-op methods, back-compat shims (pre-1.0 — rename cleanly).
- Bypassing type safety to compile; reshaping library code to satisfy a test.
- Silent DRY refactors; auto-fixing unrelated issues surfaced by check/test/clippy — report them.

Conventions:
- Errors via the core `Error` enum + `Result<T>`.
- Timekeeping is never sleep-based.
- Every `#[repr(C)]` type crossing the IPC wire has a layout regression test.
- Git deps pinned by `rev = "<sha>"` or `tag`; never bare `git` / `branch`, including
  `[patch.crates-io]`.
- Rustdoc: public items get a one-line doc; no ASCII diagrams in doc comments; use intra-doc
  ``[`Type`]`` links; `cargo doc -p streamlib --no-deps` stays warning-free.
- Platform dirs are conditionally compiled — `core/` is platform-agnostic, `apple/` and `linux/`
  are per-platform. Never put a `#[cfg]` inside a platform-specific directory.
- macOS / Apple-path changes merge only with the `Build (macOS)` CI lane green in the
  merge queue, which runs it on every change before it lands; pull requests do not. That
  lane is the gate; a cross-compile from Linux is not, because it stops in a
  dependency's build script that needs Apple's compiler and SDK.
