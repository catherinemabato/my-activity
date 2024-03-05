---
title: dfr lowercase
categories: |
  dataframe
version: 0.90.0
dataframe: |
  Lowercase the strings in the column.
usage: |
  Lowercase the strings in the column.
feature: dataframe
---

<!-- This file is automatically generated. Please edit the command in https://github.com/nushell/nushell instead. -->

# <code>{{ $frontmatter.title }}</code> for dataframe

<div class='command-title'>{{ $frontmatter.dataframe }}</div>

:::caution[warning]
Dataframe commands were not shipped in the official binaries by default, you have to build it with `--features=dataframe` flag
:::

## Signature

`> dfr lowercase {flags} `

## Input/output types:

| input | output |
| ----- | ------ |
| any   | any    |

## Examples

Modifies strings to lowercase

```nu
> [Abc aBc abC] | dfr into-df | dfr lowercase
╭───┬─────╮
│ # │  0  │
├───┼─────┤
│ 0 │ abc │
│ 1 │ abc │
│ 2 │ abc │
╰───┴─────╯

```