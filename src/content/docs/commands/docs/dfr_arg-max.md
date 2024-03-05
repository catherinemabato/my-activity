---
title: dfr arg-max
categories: |
  dataframe
version: 0.90.0
dataframe: |
  Return index for max value in series.
usage: |
  Return index for max value in series.
feature: dataframe
---

<!-- This file is automatically generated. Please edit the command in https://github.com/nushell/nushell instead. -->

# <code>{{ $frontmatter.title }}</code> for dataframe

<div class='command-title'>{{ $frontmatter.dataframe }}</div>

:::caution[warning]
Dataframe commands were not shipped in the official binaries by default, you have to build it with `--features=dataframe` flag
:::

## Signature

`> dfr arg-max {flags} `

## Input/output types:

| input | output |
| ----- | ------ |
| any   | any    |

## Examples

Returns index for max value

```nu
> [1 3 2] | dfr into-df | dfr arg-max
╭───┬─────────╮
│ # │ arg_max │
├───┼─────────┤
│ 0 │       1 │
╰───┴─────────╯

```