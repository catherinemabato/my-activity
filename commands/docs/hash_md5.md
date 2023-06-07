---
title: hash md5
categories: |
  hash
version: 0.81.0
hash: |
  Hash a value using the md5 hash algorithm
usage: |
  Hash a value using the md5 hash algorithm
---

# <code>{{ $frontmatter.title }}</code> for hash

<div class='command-title'>{{ $frontmatter.hash }}</div>

## Signature

```> hash md5 ...rest --binary```

## Parameters

 -  `...rest`: optionally md5 hash data by cell path
 -  `--binary` `(-b)`: Output binary instead of hexadecimal representation

## Examples

Return the md5 hash of a string, hex-encoded
```shell
> 'abcdefghijklmnopqrstuvwxyz' | hash md5
c3fcd3d76192e4007dfb496cca67e13b
```

Return the md5 hash of a string, as binary
```shell
> 'abcdefghijklmnopqrstuvwxyz' | hash md5 --binary
Length: 16 (0x10) bytes | printable whitespace ascii_other non_ascii
00000000:   c3 fc d3 d7  61 92 e4 00  7d fb 49 6c  ca 67 e1 3b   ××××a××0}×Il×g×;

```

Return the md5 hash of a file's contents
```shell
> open ./nu_0_24_1_windows.zip | hash md5

```
