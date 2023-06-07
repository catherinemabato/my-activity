---
title: from nuon
categories: |
  experimental
version: 0.81.0
experimental: |
  Convert from nuon to structured data.
usage: |
  Convert from nuon to structured data.
---

# <code>{{ $frontmatter.title }}</code> for experimental

<div class='command-title'>{{ $frontmatter.experimental }}</div>

## Signature

```> from nuon ```

## Examples

Converts nuon formatted string to table
```shell
> '{ a:1 }' | from nuon
╭───┬───╮
│ a │ 1 │
╰───┴───╯
```

Converts nuon formatted string to table
```shell
> '{ a:1, b: [1, 2] }' | from nuon
╭───┬───────────╮
│ a │ 1         │
│   │ ╭───┬───╮ │
│ b │ │ 0 │ 1 │ │
│   │ │ 1 │ 2 │ │
│   │ ╰───┴───╯ │
╰───┴───────────╯
```
