---
title: math tau
categories: |
  math
version: 0.81.0
math: |
  Returns the mathematical constant τ.
usage: |
  Returns the mathematical constant τ.
---

# <code>{{ $frontmatter.title }}</code> for math

<div class='command-title'>{{ $frontmatter.math }}</div>

## Signature

```> math tau ```

## Examples

Get the first two decimal digits of τ
```shell
> math tau | math round --precision 2
6.28
```
