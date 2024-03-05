---
title: to csv
categories: |
  formats
version: 0.90.0
formats: |
  Convert table into .csv text .
usage: |
  Convert table into .csv text .
feature: default
---

<!-- This file is automatically generated. Please edit the command in https://github.com/nushell/nushell instead. -->

# <code>{{ $frontmatter.title }}</code> for formats

<div class='command-title'>{{ $frontmatter.formats }}</div>

## Signature

`> to csv {flags} `

## Flags

- `--separator, -s {string}`: a character to separate columns, defaults to ','
- `--noheaders, -n`: do not output the columns names as the first row

## Input/output types:

| input  | output |
| ------ | ------ |
| record | string |
| table  | string |

## Examples

Outputs an CSV string representing the contents of this table

```nu
> [[foo bar]; [1 2]] | to csv
foo,bar
1,2

```

Outputs an CSV string representing the contents of this table

```nu
> [[foo bar]; [1 2]] | to csv --separator ';'
foo;bar
1;2

```

Outputs an CSV string representing the contents of this record

```nu
> {a: 1 b: 2} | to csv
a,b
1,2

```