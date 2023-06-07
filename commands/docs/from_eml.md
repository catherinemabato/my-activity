---
title: from eml
categories: |
  formats
version: 0.81.0
formats: |
  Parse text as .eml and create record.
usage: |
  Parse text as .eml and create record.
---

# <code>{{ $frontmatter.title }}</code> for formats

<div class='command-title'>{{ $frontmatter.formats }}</div>

## Signature

```> from eml --preview-body```

## Parameters

 -  `--preview-body {int}`: How many bytes of the body to preview

## Examples

Convert eml structured data into record
```shell
> 'From: test@email.com
Subject: Welcome
To: someone@somewhere.com
Test' | from eml
╭─────────┬─────────────────────────────────────╮
│ Subject │ Welcome                             │
│         │ ╭─────────┬────────────────╮        │
│ From    │ │ Name    │                │        │
│         │ │ Address │ test@email.com │        │
│         │ ╰─────────┴────────────────╯        │
│         │ ╭─────────┬───────────────────────╮ │
│ To      │ │ Name    │                       │ │
│         │ │ Address │ someone@somewhere.com │ │
│         │ ╰─────────┴───────────────────────╯ │
│ Body    │ Test                                │
╰─────────┴─────────────────────────────────────╯
```

Convert eml structured data into record
```shell
> 'From: test@email.com
Subject: Welcome
To: someone@somewhere.com
Test' | from eml -b 1
╭─────────┬─────────────────────────────────────╮
│ Subject │ Welcome                             │
│         │ ╭─────────┬────────────────╮        │
│ From    │ │ Name    │                │        │
│         │ │ Address │ test@email.com │        │
│         │ ╰─────────┴────────────────╯        │
│         │ ╭─────────┬───────────────────────╮ │
│ To      │ │ Name    │                       │ │
│         │ │ Address │ someone@somewhere.com │ │
│         │ ╰─────────┴───────────────────────╯ │
│ Body    │ T                                   │
╰─────────┴─────────────────────────────────────╯
```
