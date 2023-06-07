---
title: transpose
categories: |
  default
version: 0.81.0
default: |
  Transposes the table contents so rows become columns and columns become rows.
usage: |
  Transposes the table contents so rows become columns and columns become rows.
---

# <code>{{ $frontmatter.title }}</code> for default

<div class='command-title'>{{ $frontmatter.default }}</div>

## Signature

```> transpose ...rest --header-row --ignore-titles --as-record --keep-last --keep-all```

## Parameters

 -  `...rest`: the names to give columns once transposed
 -  `--header-row` `(-r)`: treat the first row as column names
 -  `--ignore-titles` `(-i)`: don't transpose the column names into values
 -  `--as-record` `(-d)`: transfer to record if the result is a table and contains only one row
 -  `--keep-last` `(-l)`: on repetition of record fields due to `header-row`, keep the last value obtained
 -  `--keep-all` `(-a)`: on repetition of record fields due to `header-row`, keep all the values obtained

## Examples

Transposes the table contents with default column names
```shell
> [[c1 c2]; [1 2]] | transpose
╭───┬─────────┬─────────╮
│ # │ column0 │ column1 │
├───┼─────────┼─────────┤
│ 0 │ c1      │       1 │
│ 1 │ c2      │       2 │
╰───┴─────────┴─────────╯

```

Transposes the table contents with specified column names
```shell
> [[c1 c2]; [1 2]] | transpose key val
╭───┬─────┬─────╮
│ # │ key │ val │
├───┼─────┼─────┤
│ 0 │ c1  │   1 │
│ 1 │ c2  │   2 │
╰───┴─────┴─────╯

```

Transposes the table without column names and specify a new column name
```shell
> [[c1 c2]; [1 2]] | transpose -i val
╭───┬─────╮
│ # │ val │
├───┼─────┤
│ 0 │   1 │
│ 1 │   2 │
╰───┴─────╯

```

Transfer back to record with -d flag
```shell
> {c1: 1, c2: 2} | transpose | transpose -i -r -d
╭────┬───╮
│ c1 │ 1 │
│ c2 │ 2 │
╰────┴───╯
```
