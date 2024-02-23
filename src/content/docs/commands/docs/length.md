---
title: length
categories: |
  filters
version: 0.90.0
filters: |
  Count the number of items in an input list or rows in a table.
usage: |
  Count the number of items in an input list or rows in a table.
feature: default
---

<!-- This file is automatically generated. Please edit the command in https://github.com/nushell/nushell instead. -->

# <code>{{ $frontmatter.title }}</code> for filters

<div class='command-title'>{{ $frontmatter.filters }}</div>

## Signature

`> length {flags} `

## Input/output types:

| input       | output |
| ----------- | ------ |
| list\<any\> | int    |

## Examples

Count the number of items in a list

```nu
> [1 2 3 4 5] | length
5
```

Count the number of rows in a table

```nu
> [{a:1 b:2}, {a:2 b:3}] | length
2
```