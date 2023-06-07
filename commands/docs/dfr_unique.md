---
title: dfr unique
categories: |
  dataframe or lazyframe
version: 0.81.0
dataframe_or_lazyframe: |
  Returns unique values from a dataframe.
usage: |
  Returns unique values from a dataframe.
---

# <code>{{ $frontmatter.title }}</code> for dataframe or lazyframe

<div class='command-title'>{{ $frontmatter.dataframe_or_lazyframe }}</div>

## Signature

```> dfr unique --subset --last --maintain-order```

## Parameters

 -  `--subset {any}`: Subset of column(s) to use to maintain rows (lazy df)
 -  `--last` `(-l)`: Keeps last unique value. Default keeps first value (lazy df)
 -  `--maintain-order` `(-k)`: Keep the same order as the original DataFrame (lazy df)

## Examples

Returns unique values from a series
```shell
> [2 2 2 2 2] | dfr into-df | dfr unique
╭───┬───╮
│ # │ 0 │
├───┼───┤
│ 0 │ 2 │
╰───┴───╯

```

Creates a is unique expression from a column
```shell
> col a | unique

```
