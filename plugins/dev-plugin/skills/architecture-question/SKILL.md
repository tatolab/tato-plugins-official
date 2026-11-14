---
name: architecture-question
description: Answer how something in the system works, with evidence, labelled by source. Use when the owner asks "how does X work", "why is Y shaped this way", "what happens when Z" — a question about behaviour or structure, not a request to change it.
---

# Architecture question

The result is shared understanding, so this is a read-only pass.

1. **Read the code paths before answering**, every platform variant included, and the other
   repo's side when the answer depends on it. An answer from memory is how wrong beliefs settle in.
2. **Label each part of the answer by its source**:
   - **[CODE]** — what the tree does today, with `file:line`. Code is the only source of truth.
   - **[INFERRED]** — your reconstruction or judgment, with how confident you are.
3. **End by saying your understanding back in one paragraph** and asking whether it matches the
   owner's.
