---
title: math product
categories: |
  math
version: 0.90.0
math: |
  Returns the product of a list of numbers or the products of each column of a table.
usage: |
  Returns the product of a list of numbers or the products of each column of a table.
feature: default
---

<!-- This file is automatically generated. Please edit the command in https://github.com/nushell/nushell instead. -->

# <code>{{ $frontmatter.title }}</code> for math

<div class='command-title'>{{ $frontmatter.math }}</div>

## Signature

`> math product {flags} `

## Input/output types:

| input          | output |
| -------------- | ------ |
| list\<number\> | number |
| range          | number |
| record         | record |
| table          | record |

## Examples

Compute the product of a list of numbers

```nu
> [2 3 3 4] | math product
72
```

Compute the product of each column in a table

```nu
> [[a b]; [1 2] [3 4]] | math product
╭───┬───╮
│ a │ 3 │
│ b │ 8 │
╰───┴───╯
```