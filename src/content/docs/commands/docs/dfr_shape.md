---
title: dfr shape
categories: |
  dataframe
version: 0.90.0
dataframe: |
  Shows column and row size for a dataframe.
usage: |
  Shows column and row size for a dataframe.
feature: dataframe
---

<!-- This file is automatically generated. Please edit the command in https://github.com/nushell/nushell instead. -->

# <code>{{ $frontmatter.title }}</code> for dataframe

<div class='command-title'>{{ $frontmatter.dataframe }}</div>

:::caution[warning]
Dataframe commands were not shipped in the official binaries by default, you have to build it with `--features=dataframe` flag
:::

## Signature

`> dfr shape {flags} `

## Input/output types:

| input | output |
| ----- | ------ |
| any   | any    |

## Examples

Shows row and column shape

```nu
> [[a b]; [1 2] [3 4]] | dfr into-df | dfr shape
╭───┬──────┬─────────╮
│ # │ rows │ columns │
├───┼──────┼─────────┤
│ 0 │    2 │       2 │
╰───┴──────┴─────────╯

```