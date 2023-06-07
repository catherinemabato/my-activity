---
title: math round
categories: |
  math
version: 0.81.0
math: |
  Returns the input number rounded to the specified precision.
usage: |
  Returns the input number rounded to the specified precision.
---

# <code>{{ $frontmatter.title }}</code> for math

<div class='command-title'>{{ $frontmatter.math }}</div>

## Signature

```> math round --precision```

## Parameters

 -  `--precision {number}`: digits of precision

## Examples

Apply the round function to a list of numbers
```shell
> [1.5 2.3 -3.1] | math round
╭───┬────╮
│ 0 │  2 │
│ 1 │  2 │
│ 2 │ -3 │
╰───┴────╯

```

Apply the round function with precision specified
```shell
> [1.555 2.333 -3.111] | math round -p 2
╭───┬─────────╮
│ 0 │  1.5600 │
│ 1 │  2.3300 │
│ 2 │ -3.1100 │
╰───┴─────────╯

```

Apply negative precision to a list of numbers
```shell
> [123, 123.3, -123.4] | math round -p -1
╭───┬──────╮
│ 0 │  120 │
│ 1 │  120 │
│ 2 │ -120 │
╰───┴──────╯

```
