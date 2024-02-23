---
title: dfr as-date
categories: |
  dataframe
version: 0.90.0
dataframe: |
  Converts string to date.
usage: |
  Converts string to date.
feature: dataframe
---

<!-- This file is automatically generated. Please edit the command in https://github.com/nushell/nushell instead. -->

# <code>{{ $frontmatter.title }}</code> for dataframe

<div class='command-title'>{{ $frontmatter.dataframe }}</div>

:::caution[warning]
Dataframe commands were not shipped in the official binaries by default, you have to build it with `--features=dataframe` flag
:::

## Signature

`> dfr as-date {flags} (format)`

## Flags

- `--not-exact, -n`: the format string may be contained in the date (e.g. foo-2021-01-01-bar could match 2021-01-01)

## Parameters

- `format`: formatting date string

## Input/output types:

| input | output |
| ----- | ------ |
| any   | any    |

## Examples

Converts string to date

```nu
> ["2021-12-30" "2021-12-31"] | dfr into-df | dfr as-datetime "%Y-%m-%d"

```

## Notes

Format example:
"%Y-%m-%d" => 2021-12-31
"%d-%m-%Y" => 31-12-2021
"%Y%m%d" => 2021319 (2021-03-19)