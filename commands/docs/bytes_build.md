---
title: bytes build
categories: |
  bytes
version: 0.81.0
bytes: |
  Create bytes from the arguments.
usage: |
  Create bytes from the arguments.
---

# <code>{{ $frontmatter.title }}</code> for bytes

<div class='command-title'>{{ $frontmatter.bytes }}</div>

## Signature

```> bytes build ...rest```

## Parameters

 -  `...rest`: list of bytes

## Examples

Builds binary data from 0x[01 02], 0x[03], 0x[04]
```shell
> bytes build 0x[01 02] 0x[03] 0x[04]
Length: 4 (0x4) bytes | printable whitespace ascii_other non_ascii
00000000:   01 02 03 04                                          ••••

```
