---
name: snapshot-architecture
description: Rebuild the code-derived architecture snapshot — Claude's current understanding of how the system actually works — as a living Claude Artifact with Mermaid diagrams and code references. Use when the owner wants the snapshot refreshed or wants a shared picture to discuss and correct.
---

# Snapshot architecture

Code is the only source of truth. The snapshot is derived from code alone and leaves the
code untouched; the fixes it surfaces happen afterwards, where they belong.

1. **Survey, read-only.** Fan out Explore/domain-expert subagents across `runtime/`,
   `sdk/`, `adapters/`, `xtask/` — what subsystems exist, how they connect,
   what the real boundaries and data flows are. Every claim needs a source
   (`file:line` or path); anything not verified in the tree is labeled INFERRED.
2. **Load the `artifact-design` skill**, then build one HTML page:
   - A top-level system diagram plus per-subsystem sections, each with a Mermaid diagram
     (```mermaid fences render natively in artifacts) and prose.
   - Every claim tagged **[VERIFIED path:line]** or **[INFERRED — confidence]**.
   - An **open questions** section — the things Claude is least sure it understands,
     explicitly inviting correction.
3. **Publish as ONE living artifact.** Stable title "StreamLib Architecture Snapshot
   (code view)", stable favicon. In a session that didn't create it, find it with the
   Artifact tool's `action: "list"` and pass its `url` to redeploy — never mint a second
   snapshot URL, so the owner's link stays live.
4. **Close the loop.** A regression it surfaces is a Linear `Bug` issue; the snapshot is
   regenerated after a fix.
