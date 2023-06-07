---
title: length
categories: |
  filters
version: 0.81.0
filters: |
  Count the number of elements in the input.
usage: |
  Count the number of elements in the input.
---

# <code>{{ $frontmatter.title }}</code> for filters

<div class='command-title'>{{ $frontmatter.filters }}</div>

## Signature

```> length --column```

## Parameters

 -  `--column` `(-c)`: Show the number of columns in a table

## Examples

Count the number of items in a list
```shell
> [1 2 3 4 5] | length
5
```

Count the number of columns in a table
```shell
> [{columnA: A0 columnB: B0}] | length -c
2
```
