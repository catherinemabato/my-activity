---
title: hash sha256
categories: |
  hash
version: 0.76.1
hash: |
  Hash a value using the sha256 hash algorithm
usage: |
  Hash a value using the sha256 hash algorithm
---

# <code>{{ $frontmatter.title }}</code> for hash

<div class='command-title'>{{ $frontmatter.hash }}</div>

## Signature

```> hash sha256 ...rest --binary```

## Parameters

 -  `...rest`: optionally sha256 hash data by cell path
 -  `--binary` `(-b)`: Output binary instead of hexadecimal representation

## Examples

Return the sha256 hash of a string, hex-encoded
```shell
> 'abcdefghijklmnopqrstuvwxyz' | hash sha256
```

Return the sha256 hash of a string, as binary
```shell
> 'abcdefghijklmnopqrstuvwxyz' | hash sha256 --binary
```

Return the sha256 hash of a file's contents
```shell
> open ./nu_0_24_1_windows.zip | hash sha256
```
