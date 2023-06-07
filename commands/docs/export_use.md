---
title: export use
categories: |
  core
version: 0.81.0
core: |
  Use definitions from a module and export them from this module.
usage: |
  Use definitions from a module and export them from this module.
---

# <code>{{ $frontmatter.title }}</code> for core

<div class='command-title'>{{ $frontmatter.core }}</div>

## Signature

```> export use (module) (members)```

## Parameters

 -  `module`: Module or module file
 -  `members`: Which members of the module to import

## Notes
This command is a parser keyword. For details, check:
  https://www.nushell.sh/book/thinking_in_nu.html
## Examples

Re-export a command from another module
```shell
> module spam { export def foo [] { "foo" } }
    module eggs { export use spam foo }
    use eggs foo
    foo

foo
```
