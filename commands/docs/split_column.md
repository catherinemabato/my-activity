---
title: split column
categories: |
  strings
version: 0.81.0
strings: |
  Split a string into multiple columns using a separator.
usage: |
  Split a string into multiple columns using a separator.
---

# <code>{{ $frontmatter.title }}</code> for strings

<div class='command-title'>{{ $frontmatter.strings }}</div>

## Signature

```> split column (separator) ...rest --collapse-empty --regex```

## Parameters

 -  `separator`: the character or string that denotes what separates columns
 -  `...rest`: column names to give the new columns
 -  `--collapse-empty` `(-c)`: remove empty columns
 -  `--regex` `(-r)`: separator is a regular expression

## Examples

Split a string into columns by the specified separator
```shell
> 'a--b--c' | split column '--'
╭───┬─────────┬─────────┬─────────╮
│ # │ column1 │ column2 │ column3 │
├───┼─────────┼─────────┼─────────┤
│ 0 │ a       │ b       │ c       │
╰───┴─────────┴─────────┴─────────╯

```

Split a string into columns of char and remove the empty columns
```shell
> 'abc' | split column -c ''
╭───┬─────────┬─────────┬─────────╮
│ # │ column1 │ column2 │ column3 │
├───┼─────────┼─────────┼─────────┤
│ 0 │ a       │ b       │ c       │
╰───┴─────────┴─────────┴─────────╯

```

Split a list of strings into a table
```shell
> ['a-b' 'c-d'] | split column -
╭───┬─────────┬─────────╮
│ # │ column1 │ column2 │
├───┼─────────┼─────────┤
│ 0 │ a       │ b       │
│ 1 │ c       │ d       │
╰───┴─────────┴─────────╯

```

Split a list of strings into a table, ignoring padding
```shell
> ['a -  b' 'c  -    d'] | split column -r '\s*-\s*'
╭───┬─────────┬─────────╮
│ # │ column1 │ column2 │
├───┼─────────┼─────────┤
│ 0 │ a       │ b       │
│ 1 │ c       │ d       │
╰───┴─────────┴─────────╯

```
