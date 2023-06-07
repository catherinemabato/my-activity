---
title: bytes reverse
categories: |
  bytes
version: 0.81.0
bytes: |
  Reverse the bytes in the pipeline.
usage: |
  Reverse the bytes in the pipeline.
---

# <code>{{ $frontmatter.title }}</code> for bytes

<div class='command-title'>{{ $frontmatter.bytes }}</div>

## Signature

```> bytes reverse ...rest```

## Parameters

 -  `...rest`: for a data structure input, reverse data at the given cell paths

## Examples

Reverse bytes `0x[1F FF AA AA]`
```shell
> 0x[1F FF AA AA] | bytes reverse
Length: 4 (0x4) bytes | printable whitespace ascii_other non_ascii
00000000:   aa aa ff 1f                                          ×××•

```

Reverse bytes `0x[FF AA AA]`
```shell
> 0x[FF AA AA] | bytes reverse
Length: 3 (0x3) bytes | printable whitespace ascii_other non_ascii
00000000:   aa aa ff                                             ×××

```
