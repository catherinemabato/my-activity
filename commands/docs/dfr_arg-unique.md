---
title: dfr arg-unique
categories: |
  dataframe
version: 0.81.0
dataframe: |
  Returns indexes for unique values.
usage: |
  Returns indexes for unique values.
---

# <code>{{ $frontmatter.title }}</code> for dataframe

<div class='command-title'>{{ $frontmatter.dataframe }}</div>

## Signature

```> dfr arg-unique ```

## Examples

Returns indexes for unique values
```shell
> [1 2 2 3 3] | dfr into-df | dfr arg-unique
╭───┬────────────╮
│ # │ arg_unique │
├───┼────────────┤
│ 0 │          0 │
│ 1 │          1 │
│ 2 │          3 │
╰───┴────────────╯

```
