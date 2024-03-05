---
title: query web
categories: |
  network
version: 0.90.0
network: |
  execute selector query on html/web
usage: |
  execute selector query on html/web
feature: default
---

<!-- This file is automatically generated. Please edit the command in https://github.com/nushell/nushell instead. -->

# <code>{{ $frontmatter.title }}</code> for network

<div class='command-title'>{{ $frontmatter.network }}</div>

## Signature

`> query web {flags} `

## Flags

- `--query, -q {string}`: selector query
- `--as-html, -m`: return the query output as html
- `--attribute, -a {string}`: downselect based on the given attribute
- `--as-table, -t {list<string>}`: find table based on column header list
- `--inspect, -i`: run in inspect mode to provide more information for determining column headers

## Input/output types:

| input | output |
| ----- | ------ |
| any   | any    |

## Examples

Retrieve all `<header>` elements from phoronix.com website

```nu
> http get https://phoronix.com | query web --query 'header' | flatten

```

Retrieve a html table from Wikipedia and parse it into a nushell table using table headers as guides

```nu
> http get https://en.wikipedia.org/wiki/List_of_cities_in_India_by_population |
    query web --as-table [City 'Population(2011)[3]' 'Population(2001)[3][a]' 'State or unionterritory' 'Ref']

```

Pass multiple css selectors to extract several elements within single query, group the query results together and rotate them to create a table

```nu
> http get https://www.nushell.sh | query web --query 'h2, h2 + p' | each {str join} | group 2 | each {rotate --ccw tagline description} | flatten

```

Retrieve a specific html attribute instead of the default text

```nu
> http get https://example.org | query web --query a --attribute href

```