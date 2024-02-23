---
title: format filesize
categories: |
  strings
version: 0.90.0
strings: |
  Converts a column of filesizes to some specified format.
usage: |
  Converts a column of filesizes to some specified format.
feature: default
---

<!-- This file is automatically generated. Please edit the command in https://github.com/nushell/nushell instead. -->

# <code>{{ $frontmatter.title }}</code> for strings

<div class='command-title'>{{ $frontmatter.strings }}</div>

## Signature

`> format filesize {flags} (format value) ...rest`

## Parameters

- `format value`: The format into which convert the file sizes.
- `...rest`: For a data structure input, format filesizes at the given cell paths.

## Input/output types:

| input    | output |
| -------- | ------ |
| filesize | string |
| record   | record |
| table    | table  |

## Examples

Convert the size column to KB

```nu
> ls | format filesize KB size

```

Convert the apparent column to B

```nu
> du | format filesize B apparent

```

Convert the size data to MB

```nu
> 4Gb | format filesize MB
4000.0 MB
```