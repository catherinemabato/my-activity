---
title: path split
categories: |
  default
version: 0.76.0
default: |
  Split a path into a list based on the system's path separator.
usage: |
  Split a path into a list based on the system's path separator.
---

# <code>{{ $frontmatter.title }}</code> for default

<div class='command-title'>{{ $frontmatter.default }}</div>

## Signature

```> path split --columns```

## Parameters

 -  `--columns {table}`: For a record or table input, split strings at the given columns

## Examples

Split a path into parts
```shell
> 'C:\Users\viking\spam.txt' | path split
```

Split all paths under the 'name' column
```shell
> ls ('.' | path expand) | path split -c [ name ]
```
