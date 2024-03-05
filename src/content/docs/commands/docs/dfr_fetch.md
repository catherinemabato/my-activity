---
title: dfr fetch
categories: |
  lazyframe
version: 0.90.0
lazyframe: |
  Collects the lazyframe to the selected rows.
usage: |
  Collects the lazyframe to the selected rows.
feature: dataframe
---

<!-- This file is automatically generated. Please edit the command in https://github.com/nushell/nushell instead. -->

# <code>{{ $frontmatter.title }}</code> for lazyframe

<div class='command-title'>{{ $frontmatter.lazyframe }}</div>

:::caution[warning]
Dataframe commands were not shipped in the official binaries by default, you have to build it with `--features=dataframe` flag
:::

## Signature

`> dfr fetch {flags} (rows)`

## Parameters

- `rows`: number of rows to be fetched from lazyframe

## Input/output types:

| input | output |
| ----- | ------ |
| any   | any    |

## Examples

Fetch a rows from the dataframe

```nu
> [[a b]; [6 2] [4 2] [2 2]] | dfr into-df | dfr fetch 2
╭───┬───┬───╮
│ # │ a │ b │
├───┼───┼───┤
│ 0 │ 6 │ 2 │
│ 1 │ 4 │ 2 │
╰───┴───┴───╯

```