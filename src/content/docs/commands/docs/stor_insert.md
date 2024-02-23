---
title: stor insert
categories: |
  database
version: 0.90.0
database: |
  Insert information into a specified table in the in-memory sqlite database.
usage: |
  Insert information into a specified table in the in-memory sqlite database.
feature: default
---

<!-- This file is automatically generated. Please edit the command in https://github.com/nushell/nushell instead. -->

# <code>{{ $frontmatter.title }}</code> for database

<div class='command-title'>{{ $frontmatter.database }}</div>

## Signature

`> stor insert {flags} `

## Flags

- `--table-name, -t {string}`: name of the table you want to insert into
- `--data-record, -d {record}`: a record of column names and column values to insert into the specified table

## Input/output types:

| input   | output |
| ------- | ------ |
| nothing | table  |

## Examples

Insert data the in-memory sqlite database using a data-record of column-name and column-value pairs

```nu
> stor insert --table-name nudb --data-record {bool1: true, int1: 5, float1: 1.1, str1: fdncred, datetime1: 2023-04-17}

```