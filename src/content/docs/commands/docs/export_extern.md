---
title: export extern
categories: |
  core
version: 0.90.0
core: |
  Define an extern and export it from a module.
usage: |
  Define an extern and export it from a module.
feature: default
---

<!-- This file is automatically generated. Please edit the command in https://github.com/nushell/nushell instead. -->

# <code>{{ $frontmatter.title }}</code> for core

<div class='command-title'>{{ $frontmatter.core }}</div>

## Signature

`> export extern {flags} (def_name) (params)`

## Parameters

- `def_name`: Definition name.
- `params`: Parameters.

## Input/output types:

| input   | output  |
| ------- | ------- |
| nothing | nothing |

## Examples

Export the signature for an external command

```nu
> export extern echo [text: string]

```

## Notes

This command is a parser keyword. For details, check:
https://www.nushell.sh/book/thinking_in_nu.html