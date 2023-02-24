---
title: path parse
categories: |
  default
version: 0.76.0
default: |
  Convert a path into structured data.
usage: |
  Convert a path into structured data.
---

# <code>{{ $frontmatter.title }}</code> for default

<div class='command-title'>{{ $frontmatter.default }}</div>

## Signature

```> path parse --columns --extension```

## Parameters

 -  `--columns {table}`: For a record or table input, convert strings at the given columns
 -  `--extension {string}`: Manually supply the extension (without the dot)

## Notes
Each path is split into a table with 'parent', 'stem' and 'extension' fields.
On Windows, an extra 'prefix' column is added.
## Examples

Parse a single path
```shell
> 'C:\Users\viking\spam.txt' | path parse
```

Replace a complex extension
```shell
> 'C:\Users\viking\spam.tar.gz' | path parse -e tar.gz | upsert extension { 'txt' }
```

Ignore the extension
```shell
> 'C:\Users\viking.d' | path parse -e ''
```

Parse all paths under the 'name' column
```shell
> ls | path parse -c [ name ]
```
