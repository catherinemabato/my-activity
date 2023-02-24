---
title: commandline
categories: |
  core
version: 0.76.0
core: |
  View or modify the current command line input buffer
usage: |
  View or modify the current command line input buffer
---

# <code>{{ $frontmatter.title }}</code> for core

<div class='command-title'>{{ $frontmatter.core }}</div>

## Signature

```> commandline (cmd) --append --insert --replace```

## Parameters

 -  `cmd`: the string to perform the operation with
 -  `--append` `(-a)`: appends the string to the end of the buffer
 -  `--insert` `(-i)`: inserts the string into the buffer at the cursor position
 -  `--replace` `(-r)`: replaces the current contents of the buffer (default)
