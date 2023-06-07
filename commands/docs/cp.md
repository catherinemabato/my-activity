---
title: cp
categories: |
  filesystem
version: 0.81.0
filesystem: |
  Copy files.
usage: |
  Copy files.
---

# <code>{{ $frontmatter.title }}</code> for filesystem

<div class='command-title'>{{ $frontmatter.filesystem }}</div>

## Signature

```> cp (source) (destination) --recursive --verbose --update --interactive --no-symlink --progress```

## Parameters

 -  `source`: the place to copy from
 -  `destination`: the place to copy to
 -  `--recursive` `(-r)`: copy recursively through subdirectories
 -  `--verbose` `(-v)`: show successful copies in addition to failed copies (default:false)
 -  `--update` `(-u)`: copy only when the SOURCE file is newer than the destination file or when the destination file is missing
 -  `--interactive` `(-i)`: ask user to confirm action
 -  `--no-symlink` `(-n)`: no symbolic links are followed, only works if -r is active
 -  `--progress` `(-p)`: enable progress bar

## Examples

Copy myfile to dir_b
```shell
> cp myfile dir_b

```

Recursively copy dir_a to dir_b
```shell
> cp -r dir_a dir_b

```

Recursively copy dir_a to dir_b, and print the feedbacks
```shell
> cp -r -v dir_a dir_b

```

Move many files into a directory
```shell
> cp *.txt dir_a

```

Copy only if source file is newer than target file
```shell
> cp -u a b

```
