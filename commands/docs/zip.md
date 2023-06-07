---
title: zip
categories: |
  filters
version: 0.81.0
filters: |
  Combine a stream with the input.
usage: |
  Combine a stream with the input.
---

# <code>{{ $frontmatter.title }}</code> for filters

<div class='command-title'>{{ $frontmatter.filters }}</div>

## Signature

```> zip (other)```

## Parameters

 -  `other`: the other input

## Examples

Zip two lists
```shell
> [1 2] | zip [3 4]
╭───┬───────────╮
│ 0 │ ╭───┬───╮ │
│   │ │ 0 │ 1 │ │
│   │ │ 1 │ 3 │ │
│   │ ╰───┴───╯ │
│ 1 │ ╭───┬───╮ │
│   │ │ 0 │ 2 │ │
│   │ │ 1 │ 4 │ │
│   │ ╰───┴───╯ │
╰───┴───────────╯

```

Zip two ranges
```shell
> 1..3 | zip 4..6
╭───┬───────────╮
│ 0 │ ╭───┬───╮ │
│   │ │ 0 │ 1 │ │
│   │ │ 1 │ 4 │ │
│   │ ╰───┴───╯ │
│ 1 │ ╭───┬───╮ │
│   │ │ 0 │ 2 │ │
│   │ │ 1 │ 5 │ │
│   │ ╰───┴───╯ │
│ 2 │ ╭───┬───╮ │
│   │ │ 0 │ 3 │ │
│   │ │ 1 │ 6 │ │
│   │ ╰───┴───╯ │
╰───┴───────────╯

```

Rename .ogg files to match an existing list of filenames
```shell
> glob *.ogg | zip ['bang.ogg', 'fanfare.ogg', 'laser.ogg'] | each {|| mv $in.0 $in.1 }

```
