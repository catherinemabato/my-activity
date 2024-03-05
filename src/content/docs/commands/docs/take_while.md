---
title: take while
categories: |
  filters
version: 0.90.0
filters: |
  Take elements of the input while a predicate is true.
usage: |
  Take elements of the input while a predicate is true.
feature: default
---

<!-- This file is automatically generated. Please edit the command in https://github.com/nushell/nushell instead. -->

# <code>{{ $frontmatter.title }}</code> for filters

<div class='command-title'>{{ $frontmatter.filters }}</div>

## Signature

`> take while {flags} (predicate)`

## Parameters

- `predicate`: The predicate that element(s) must match.

## Input/output types:

| input       | output      |
| ----------- | ----------- |
| list\<any\> | list\<any\> |
| table       | table       |

## Examples

Take while the element is negative

```nu
> [-1 -2 9 1] | take while {|x| $x < 0 }
╭───┬────╮
│ 0 │ -1 │
│ 1 │ -2 │
╰───┴────╯

```

Take while the element is negative using stored condition

```nu
> let cond = {|x| $x < 0 }; [-1 -2 9 1] | take while $cond
╭───┬────╮
│ 0 │ -1 │
│ 1 │ -2 │
╰───┴────╯

```

Take while the field value is negative

```nu
> [{a: -1} {a: -2} {a: 9} {a: 1}] | take while {|x| $x.a < 0 }
╭───┬────╮
│ # │ a  │
├───┼────┤
│ 0 │ -1 │
│ 1 │ -2 │
╰───┴────╯

```