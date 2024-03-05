---
title: path join
categories: |
  path
version: 0.90.0
path: |
  Join a structured path or a list of path parts.
usage: |
  Join a structured path or a list of path parts.
feature: default
---

<!-- This file is automatically generated. Please edit the command in https://github.com/nushell/nushell instead. -->

# <code>{{ $frontmatter.title }}</code> for path

<div class='command-title'>{{ $frontmatter.path }}</div>

## Signature

`> path join {flags} ...rest`

## Parameters

- `...rest`: Path to append to the input.

## Input/output types:

| input          | output         |
| -------------- | -------------- |
| list\<string\> | string         |
| record         | string         |
| string         | string         |
| table          | list\<string\> |

## Examples

Append a filename to a path

```nu
> '/home/viking' | path join spam.txt
/home/viking/spam.txt
```

Append a filename to a path

```nu
> '/home/viking' | path join spams this_spam.txt
/home/viking/spams/this_spam.txt
```

Use relative paths, e.g. '..' will go up one directory

```nu
> '/home/viking' | path join .. folder
/home/viking/../folder
```

Use absolute paths, e.g. '/' will bring you to the top level directory

```nu
> '/home/viking' | path join / folder
/folder
```

Join a list of parts into a path

```nu
> [ '/' 'home' 'viking' 'spam.txt' ] | path join
/home/viking/spam.txt
```

Join a structured path into a path

```nu
> { parent: '/home/viking', stem: 'spam', extension: 'txt' } | path join
/home/viking/spam.txt
```

Join a table of structured paths into a list of paths

```nu
> [[ parent stem extension ]; [ '/home/viking' 'spam' 'txt' ]] | path join
╭───┬───────────────────────╮
│ 0 │ /home/viking/spam.txt │
╰───┴───────────────────────╯

```

## Notes

Optionally, append an additional path to the result. It is designed to accept
the output of 'path parse' and 'path split' subcommands.