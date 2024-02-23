---
title: dfr filter-with
categories: |
  dataframe or lazyframe
version: 0.90.0
dataframe_or_lazyframe: |
  Filters dataframe using a mask or expression as reference.
usage: |
  Filters dataframe using a mask or expression as reference.
feature: dataframe
---

<!-- This file is automatically generated. Please edit the command in https://github.com/nushell/nushell instead. -->

# <code>{{ $frontmatter.title }}</code> for dataframe or lazyframe

<div class='command-title'>{{ $frontmatter.dataframe_or_lazyframe }}</div>

:::caution[warning]
Dataframe commands were not shipped in the official binaries by default, you have to build it with `--features=dataframe` flag
:::

## Signature

`> dfr filter-with {flags} (mask or expression)`

## Parameters

- `mask or expression`: boolean mask used to filter data

## Input/output types:

| input | output |
| ----- | ------ |
| any   | any    |

## Examples

Filter dataframe using a bool mask

```nu
> let mask = ([true false] | dfr into-df);
    [[a b]; [1 2] [3 4]] | dfr into-df | dfr filter-with $mask
╭───┬───┬───╮
│ # │ a │ b │
├───┼───┼───┤
│ 0 │ 1 │ 2 │
╰───┴───┴───╯

```

Filter dataframe using an expression

```nu
> [[a b]; [1 2] [3 4]] | dfr into-df | dfr filter-with ((dfr col a) > 1)
╭───┬───┬───╮
│ # │ a │ b │
├───┼───┼───┤
│ 0 │ 3 │ 4 │
╰───┴───┴───╯

```