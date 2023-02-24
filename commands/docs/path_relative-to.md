---
title: path relative-to
categories: |
  default
version: 0.76.0
default: |
  Express a path as relative to another path.
usage: |
  Express a path as relative to another path.
---

# <code>{{ $frontmatter.title }}</code> for default

<div class='command-title'>{{ $frontmatter.default }}</div>

## Signature

```> path relative-to (path) --columns```

## Parameters

 -  `path`: Parent shared with the input path
 -  `--columns {table}`: For a record or table input, convert strings at the given columns

## Notes
Can be used only when the input and the argument paths are either both
absolute or both relative. The argument path needs to be a parent of the input
path.
## Examples

Find a relative path from two absolute paths
```shell
> 'C:\Users\viking' | path relative-to 'C:\Users'
```

Find a relative path from two absolute paths in a column
```shell
> ls ~ | path relative-to ~ -c [ name ]
```

Find a relative path from two relative paths
```shell
> 'eggs\bacon\sausage\spam' | path relative-to 'eggs\bacon\sausage'
```
