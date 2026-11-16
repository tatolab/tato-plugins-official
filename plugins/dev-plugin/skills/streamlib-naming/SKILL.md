---
name: streamlib-naming
description: The naming rules for tatolab/streamlib. Use when naming or reviewing a type, function, module or variable in streamlib.
---

# Naming

Names must be understood with zero context — someone reading the name 200 lines from its
declaration knows exactly what it is and where its data comes from / goes to. **Never suggest a
shorter name; suggest a more explicit one.** Explicit beats short, always.

- Encode relationship + role + direction: `FromUpstream`, `ToDownstream`, `Input`, `Output`.
- No bare generic words: never just `Writer`, `Reader`, `Handle`, `Manager`, `State`, `ctx`, `buf`.
- A node is one unit in a stream's graph. "Processor" is not a word in streamlib: say node.

Validated examples (do not shorten): `LinkOutputDataWriter`, `LinkInputDataReader`,
`LinkInputFromUpstreamNode`, `LinkOutputToDownstreamNode`,
`add_link_output_data_writer()`, `set_link_output_to_node_message_writer()`. A 43-character
name is fine.
