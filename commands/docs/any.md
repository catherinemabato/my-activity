---
title: any
categories: |
  filters
version: 0.81.0
filters: |
  Tests if any element of the input fulfills a predicate expression.
usage: |
  Tests if any element of the input fulfills a predicate expression.
---

# <code>{{ $frontmatter.title }}</code> for filters

<div class='command-title'>{{ $frontmatter.filters }}</div>

## Signature

```> any (predicate)```

## Parameters

 -  `predicate`: a closure that must evaluate to a boolean

## Examples

Check if any row's status is the string 'DOWN'
```shell
> [[status]; [UP] [DOWN] [UP]] | any {|el| $el.status == DOWN }
true
```

Check that any item is a string
```shell
> [1 2 3 4] | any {|| ($in | describe) == 'string' }
false
```

Check if any value is equal to twice its own index
```shell
> [9 8 7 6] | enumerate | any {|i| $i.item == $i.index * 2 }
true
```

Check if any of the values are odd, using a stored closure
```shell
> let cond = {|e| $e mod 2 == 1 }; [2 4 1 6 8] | any $cond
true
```
