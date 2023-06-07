---
title: match
categories: |
  core
version: 0.81.0
core: |
  Conditionally run a block on a matched value.
usage: |
  Conditionally run a block on a matched value.
---

# <code>{{ $frontmatter.title }}</code> for core

<div class='command-title'>{{ $frontmatter.core }}</div>

## Signature

```> match (value) (match_block)```

## Parameters

 -  `value`: value to check
 -  `match_block`: block to run if check succeeds

## Examples

Match on a value in range
```shell
> match 3 { 1..10 => 'yes!' }
yes!
```

Match on a field in a record
```shell
> match {a: 100} { {a: $my_value} => { $my_value } }
100
```

Match with a catch-all
```shell
> match 3 { 1 => { 'yes!' }, _ => { 'no!' } }
no!
```

Match against a list
```shell
> match [1, 2, 3] { [$a, $b, $c] => { $a + $b + $c }, _ => 0 }
6
```

Match against pipeline input
```shell
> {a: {b: 3}} | match $in {{a: { $b }} => ($b + 10) }
13
```
