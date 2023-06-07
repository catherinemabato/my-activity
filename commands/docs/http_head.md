---
title: http head
categories: |
  network
version: 0.81.0
network: |
  Get the headers from a URL.
usage: |
  Get the headers from a URL.
---

# <code>{{ $frontmatter.title }}</code> for network

<div class='command-title'>{{ $frontmatter.network }}</div>

## Signature

```> http head (URL) --user --password --max-time --headers --insecure```

## Parameters

 -  `URL`: the URL to fetch the contents from
 -  `--user {any}`: the username when authenticating
 -  `--password {any}`: the password when authenticating
 -  `--max-time {int}`: timeout period in seconds
 -  `--headers {any}`: custom headers you want to add
 -  `--insecure` `(-k)`: allow insecure server connections when using SSL

## Notes
Performs HTTP HEAD operation.
## Examples

Get headers from example.com
```shell
> http head https://www.example.com

```

Get headers from example.com, with username and password
```shell
> http head -u myuser -p mypass https://www.example.com

```

Get headers from example.com, with custom header
```shell
> http head -H [my-header-key my-header-value] https://www.example.com

```
