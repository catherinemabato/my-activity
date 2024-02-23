---
title: str pascal-case
categories: |
  strings
version: 0.90.0
strings: |
  Convert a string to PascalCase.
usage: |
  Convert a string to PascalCase.
feature: extra
---

<!-- This file is automatically generated. Please edit the command in https://github.com/nushell/nushell instead. -->

# <code>{{ $frontmatter.title }}</code> for strings

<div class='command-title'>{{ $frontmatter.strings }}</div>

:::caution[warning]
Command `str pascal-case` was not included in the official binaries by default, you have to build it with `--features=extra` flag
:::

## Signature

`> str pascal-case {flags} ...rest`

## Parameters

- `...rest`: For a data structure input, convert strings at the given cell paths

## Input/output types:

| input          | output         |
| -------------- | -------------- |
| list\<string\> | list\<string\> |
| record         | record         |
| string         | string         |
| table          | table          |

## Examples

convert a string to PascalCase

```nu
> 'nu-shell' | str pascal-case
NuShell
```

convert a string to PascalCase

```nu
> 'this-is-the-first-case' | str pascal-case
ThisIsTheFirstCase
```

convert a string to PascalCase

```nu
> 'this_is_the_second_case' | str pascal-case
ThisIsTheSecondCase
```

convert a column from a table to PascalCase

```nu
> [[lang, gems]; [nu_test, 100]] | str pascal-case lang
╭───┬────────┬──────╮
│ # │  lang  │ gems │
├───┼────────┼──────┤
│ 0 │ NuTest │  100 │
╰───┴────────┴──────╯

```