---
title: path basename
categories: |
  default
version: 0.76.0
default: |
  Get the final component of a path
usage: |
  Get the final component of a path
---

# <code>{{ $frontmatter.title }}</code> for default

<div class='command-title'>{{ $frontmatter.default }}</div>

## Signature

```> path basename --columns --replace```

## Parameters

 -  `--columns {table}`: For a record or table input, convert strings in the given columns to their basename
 -  `--replace {string}`: Return original path with basename replaced by this string

## Examples

Get basename of a path
```shell
> 'C:\Users\joe\test.txt' | path basename
```

Get basename of a path in a column
```shell
> ls .. | path basename -c [ name ]
```

Get basename of a path in a column
```shell
> [[name];[C:\Users\Joe]] | path basename -c [ name ]
```

Replace basename of a path
```shell
> 'C:\Users\joe\test.txt' | path basename -r 'spam.png'
```
