---
title: module
categories: |
  core
version: 0.81.0
core: |
  Define a custom module.
usage: |
  Define a custom module.
---

# <code>{{ $frontmatter.title }}</code> for core

<div class='command-title'>{{ $frontmatter.core }}</div>

## Signature

```> module (module) (block)```

## Parameters

 -  `module`: module name or module path
 -  `block`: body of the module if 'module' parameter is not a module path

## Notes
This command is a parser keyword. For details, check:
  https://www.nushell.sh/book/thinking_in_nu.html
## Examples

Define a custom command in a module and call it
```shell
> module spam { export def foo [] { "foo" } }; use spam foo; foo
foo
```

Define an environment variable in a module
```shell
> module foo { export-env { let-env FOO = "BAZ" } }; use foo; $env.FOO
BAZ
```

Define a custom command that participates in the environment in a module and call it
```shell
> module foo { export def-env bar [] { let-env FOO_BAR = "BAZ" } }; use foo bar; bar; $env.FOO_BAR
BAZ
```
