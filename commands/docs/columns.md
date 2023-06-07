---
title: columns
categories: |
  filters
version: 0.81.0
filters: |
  Given a record or table, produce a list of its columns' names.
usage: |
  Given a record or table, produce a list of its columns' names.
---

# <code>{{ $frontmatter.title }}</code> for filters

<div class='command-title'>{{ $frontmatter.filters }}</div>

## Signature

```> columns ```

## Notes
This is a counterpart to `values`, which produces a list of columns' values.
## Examples

Get the columns from the record
```shell
> { acronym:PWD, meaning:'Print Working Directory' } | columns
╭───┬─────────╮
│ 0 │ acronym │
│ 1 │ meaning │
╰───┴─────────╯

```

Get the columns from the table
```shell
> [[name,age,grade]; [bill,20,a]] | columns
╭───┬───────╮
│ 0 │ name  │
│ 1 │ age   │
│ 2 │ grade │
╰───┴───────╯

```

Get the first column from the table
```shell
> [[name,age,grade]; [bill,20,a]] | columns | first

```

Get the second column from the table
```shell
> [[name,age,grade]; [bill,20,a]] | columns | select 1

```
