---
title: glob
categories: |
  filesystem
version: 0.81.0
filesystem: |
  Creates a list of files and/or folders based on the glob pattern provided.
usage: |
  Creates a list of files and/or folders based on the glob pattern provided.
---

# <code>{{ $frontmatter.title }}</code> for filesystem

<div class='command-title'>{{ $frontmatter.filesystem }}</div>

## Signature

```> glob (glob) --depth --no-dir --no-file --no-symlink --not```

## Parameters

 -  `glob`: the glob expression
 -  `--depth {int}`: directory depth to search
 -  `--no-dir` `(-D)`: Whether to filter out directories from the returned paths
 -  `--no-file` `(-F)`: Whether to filter out files from the returned paths
 -  `--no-symlink` `(-S)`: Whether to filter out symlinks from the returned paths
 -  `--not {list<string>}`: Patterns to exclude from the results

## Notes
For more glob pattern help, please refer to https://github.com/olson-sean-k/wax
## Examples

Search for *.rs files
```shell
> glob *.rs

```

Search for *.rs and *.toml files recursively up to 2 folders deep
```shell
> glob **/*.{rs,toml} --depth 2

```

Search for files and folders that begin with uppercase C and lowercase c
```shell
> glob "[Cc]*"

```

Search for files and folders like abc or xyz substituting a character for ?
```shell
> glob "{a?c,x?z}"

```

A case-insensitive search for files and folders that begin with c
```shell
> glob "(?i)c*"

```

Search for files for folders that do not begin with c, C, b, M, or s
```shell
> glob "[!cCbMs]*"

```

Search for files or folders with 3 a's in a row in the name
```shell
> glob <a*:3>

```

Search for files or folders with only a, b, c, or d in the file name between 1 and 10 times
```shell
> glob <[a-d]:1,10>

```

Search for folders that begin with an uppercase ASCII letter, ignoring files and symlinks
```shell
> glob "[A-Z]*" --no-file --no-symlink

```

Search for files named tsconfig.json that are not in node_modules directories
```shell
> glob **/tsconfig.json --not [**/node_modules/**]

```

Search for all files that are not in the target nor .git directories
```shell
> glob **/* --not [**/target/** **/.git/** */]

```
