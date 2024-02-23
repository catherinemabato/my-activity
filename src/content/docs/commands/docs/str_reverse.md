---
title: str reverse
categories: |
  strings
version: 0.90.0
strings: |
  Reverse every string in the pipeline.
usage: |
  Reverse every string in the pipeline.
feature: default
---

<!-- This file is automatically generated. Please edit the command in https://github.com/nushell/nushell instead. -->

# <code>{{ $frontmatter.title }}</code> for strings

<div class='command-title'>{{ $frontmatter.strings }}</div>

## Signature

`> str reverse {flags} ...rest`

## Parameters

- `...rest`: For a data structure input, reverse strings at the given cell paths.

## Input/output types:

| input          | output         |
| -------------- | -------------- |
| list\<string\> | list\<string\> |
| record         | record         |
| string         | string         |
| table          | table          |

## Examples

Reverse a single string

```nu
> 'Nushell' | str reverse
llehsuN
```

Reverse multiple strings in a list

```nu
> ['Nushell' 'is' 'cool'] | str reverse
╭───┬─────────╮
│ 0 │ llehsuN │
│ 1 │ si      │
│ 2 │ looc    │
╰───┴─────────╯

```