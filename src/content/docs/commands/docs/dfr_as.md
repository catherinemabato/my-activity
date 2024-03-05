---
title: dfr as
categories: |
  expression
version: 0.90.0
expression: |
  Creates an alias expression.
usage: |
  Creates an alias expression.
feature: dataframe
---

<!-- This file is automatically generated. Please edit the command in https://github.com/nushell/nushell instead. -->

# <code>{{ $frontmatter.title }}</code> for expression

<div class='command-title'>{{ $frontmatter.expression }}</div>

:::caution[warning]
Dataframe commands were not shipped in the official binaries by default, you have to build it with `--features=dataframe` flag
:::

## Signature

`> dfr as {flags} (Alias name)`

## Parameters

- `Alias name`: Alias name for the expression

## Input/output types:

| input | output |
| ----- | ------ |
| any   | any    |

## Examples

Creates and alias expression

```nu
> dfr col a | dfr as new_a | dfr into-nu
╭───────┬────────────────────╮
│       │ ╭───────┬────────╮ │
│ expr  │ │ expr  │ column │ │
│       │ │ value │ a      │ │
│       │ ╰───────┴────────╯ │
│ alias │ new_a              │
╰───────┴────────────────────╯
```