---
title: ulimit
categories: |
  platform
version: 0.90.0
platform: |
  Set or get resource usage limits.
usage: |
  Set or get resource usage limits.
feature: default
---

<!-- This file is automatically generated. Please edit the command in https://github.com/nushell/nushell instead. -->

# <code>{{ $frontmatter.title }}</code> for platform

<div class='command-title'>{{ $frontmatter.platform }}</div>

## Signature

`> ulimit {flags} (limit)`

## Flags

- `--soft, -S`: Sets soft resource limit
- `--hard, -H`: Sets hard resource limit
- `--all, -a`: Prints all current limits
- `--core-size, -c`: Maximum size of core files created
- `--data-size, -d`: Maximum size of a process's data segment
- `--file-size, -f`: Maximum size of files created by the shell
- `--file-descriptor-count, -n`: Maximum number of open file descriptors
- `--stack-size, -s`: Maximum stack size
- `--cpu-time, -t`: Maximum amount of CPU time in seconds
- `--virtual-memory-size, -v`: Maximum amount of virtual memory available to each process

## Parameters

- `limit`: Limit value.

## Input/output types:

| input   | output |
| ------- | ------ |
| nothing | any    |

## Examples

Print all current limits

```nu
> ulimit -a

```

Print specified limits

```nu
> ulimit --core-size --data-size --file-size

```

Set limit

```nu
> ulimit --core-size 102400

```

Set stack size soft limit

```nu
> ulimit -s -S 10240

```

Set virtual memory size hard limit

```nu
> ulimit -v -H 10240

```

Set core size limit to unlimited

```nu
> ulimit -c unlimited

```