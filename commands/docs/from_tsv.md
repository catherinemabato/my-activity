---
title: from tsv
categories: |
  formats
version: 0.81.0
formats: |
  Parse text as .tsv and create table.
usage: |
  Parse text as .tsv and create table.
---

# <code>{{ $frontmatter.title }}</code> for formats

<div class='command-title'>{{ $frontmatter.formats }}</div>

## Signature

```> from tsv --comment --quote --escape --noheaders --flexible --no-infer --trim```

## Parameters

 -  `--comment {string}`: a comment character to ignore lines starting with it
 -  `--quote {string}`: a quote character to ignore separators in strings, defaults to '"'
 -  `--escape {string}`: an escape character for strings containing the quote character
 -  `--noheaders` `(-n)`: don't treat the first row as column names
 -  `--flexible` `(-)`: allow the number of fields in records to be variable
 -  `--no-infer` `(-)`: no field type inferencing
 -  `--trim {string}`: drop leading and trailing whitespaces around headers names and/or field values

## Examples

Convert tab-separated data to a table
```shell
> "ColA	ColB
1	2" | from tsv
╭───┬──────┬──────╮
│ # │ ColA │ ColB │
├───┼──────┼──────┤
│ 0 │    1 │    2 │
╰───┴──────┴──────╯

```

Create a tsv file with header columns and open it
```shell
> $'c1(char tab)c2(char tab)c3(char nl)1(char tab)2(char tab)3' | save tsv-data | open tsv-data | from tsv

```

Create a tsv file without header columns and open it
```shell
> $'a1(char tab)b1(char tab)c1(char nl)a2(char tab)b2(char tab)c2' | save tsv-data | open tsv-data | from tsv -n

```

Create a tsv file without header columns and open it, removing all unnecessary whitespaces
```shell
> $'a1(char tab)b1(char tab)c1(char nl)a2(char tab)b2(char tab)c2' | save tsv-data | open tsv-data | from tsv --trim all

```

Create a tsv file without header columns and open it, removing all unnecessary whitespaces in the header names
```shell
> $'a1(char tab)b1(char tab)c1(char nl)a2(char tab)b2(char tab)c2' | save tsv-data | open tsv-data | from tsv --trim headers

```

Create a tsv file without header columns and open it, removing all unnecessary whitespaces in the field values
```shell
> $'a1(char tab)b1(char tab)c1(char nl)a2(char tab)b2(char tab)c2' | save tsv-data | open tsv-data | from tsv --trim fields

```
