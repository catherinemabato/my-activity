---
title: str index-of
categories: |
  strings
version: 0.81.0
strings: |
  Returns start index of first occurrence of string in input, or -1 if no match.
usage: |
  Returns start index of first occurrence of string in input, or -1 if no match.
---

# <code>{{ $frontmatter.title }}</code> for strings

<div class='command-title'>{{ $frontmatter.strings }}</div>

## Signature

```> str index-of (string) ...rest --grapheme-clusters --utf-8-bytes --range --end```

## Parameters

 -  `string`: the string to find in the input
 -  `...rest`: For a data structure input, search strings at the given cell paths, and replace with result
 -  `--grapheme-clusters` `(-g)`: count indexes using grapheme clusters (all visible chars have length 1)
 -  `--utf-8-bytes` `(-b)`: count indexes using UTF-8 bytes (default; non-ASCII chars have length 2+)
 -  `--range {range}`: optional start and/or end index
 -  `--end` `(-e)`: search from the end of the input

## Examples

Returns index of string in input
```shell
>  'my_library.rb' | str index-of '.rb'
10
```

Count length using grapheme clusters
```shell
> '🇯🇵ほげ ふが ぴよ' | str index-of -g 'ふが'
4
```

Returns index of string in input within a`rhs open range`
```shell
>  '.rb.rb' | str index-of '.rb' -r 1..
3
```

Returns index of string in input within a lhs open range
```shell
>  '123456' | str index-of '6' -r ..4
-1
```

Returns index of string in input within a range
```shell
>  '123456' | str index-of '3' -r 1..4
2
```

Returns index of string in input
```shell
>  '/this/is/some/path/file.txt' | str index-of '/' -e
18
```
