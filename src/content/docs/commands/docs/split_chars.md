---
title: split chars
categories: |
  strings
version: 0.90.0
strings: |
  Split a string into a list of characters.
usage: |
  Split a string into a list of characters.
feature: default
---

<!-- This file is automatically generated. Please edit the command in https://github.com/nushell/nushell instead. -->

# <code>{{ $frontmatter.title }}</code> for strings

<div class='command-title'>{{ $frontmatter.strings }}</div>

## Signature

`> split chars {flags} `

## Flags

- `--grapheme-clusters, -g`: split on grapheme clusters
- `--code-points, -c`: split on code points (default; splits combined characters)

## Input/output types:

| input          | output                 |
| -------------- | ---------------------- |
| list\<string\> | list\<list\<string\>\> |
| string         | list\<string\>         |

## Examples

Split the string into a list of characters

```nu
> 'hello' | split chars
╭───┬───╮
│ 0 │ h │
│ 1 │ e │
│ 2 │ l │
│ 3 │ l │
│ 4 │ o │
╰───┴───╯

```

Split on grapheme clusters

```nu
> '🇯🇵ほげ' | split chars --grapheme-clusters
╭───┬────╮
│ 0 │ 🇯🇵 │
│ 1 │ ほ │
│ 2 │ げ │
╰───┴────╯

```

Split multiple strings into lists of characters

```nu
> ['hello', 'world'] | split chars
╭───┬───────────╮
│ 0 │ ╭───┬───╮ │
│   │ │ 0 │ h │ │
│   │ │ 1 │ e │ │
│   │ │ 2 │ l │ │
│   │ │ 3 │ l │ │
│   │ │ 4 │ o │ │
│   │ ╰───┴───╯ │
│ 1 │ ╭───┬───╮ │
│   │ │ 0 │ w │ │
│   │ │ 1 │ o │ │
│   │ │ 2 │ r │ │
│   │ │ 3 │ l │ │
│   │ │ 4 │ d │ │
│   │ ╰───┴───╯ │
╰───┴───────────╯

```