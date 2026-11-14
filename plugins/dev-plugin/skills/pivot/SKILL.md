---
name: pivot
description: A direction change — the new direction is pinned with the owner, then the legacy is inventoried and ripped out.
---

# Pivot

A pivot retires agreed architecture, so it is the owner's to declare. If implementation
surfaces a reason to pivot, raise it with the owner.

The old shape is deleted, never kept alive beside the new one.

1. **Pin the new direction** with `grilling` until it fits in five sentences and the
   owner agrees with them as written. The owner records it in Linear.
2. **Inventory the legacy,** read-only: the code paths, rules and skills the old
   direction leaves behind, and the Linear issues it orphans. Present it.
3. **Rip it out** in issues the owner files from the inventory; each removal PR proves its
   pattern is gone from the tree with a search.
4. **Cancel the orphaned issues** in Linear, each with a one-line comment naming the pivot,
   once the owner has seen the list.
