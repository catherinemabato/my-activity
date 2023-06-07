---
title: encode
categories: |
  strings
version: 0.81.0
strings: |
  Encode a string into bytes.
usage: |
  Encode a string into bytes.
---

# <code>{{ $frontmatter.title }}</code> for strings

<div class='command-title'>{{ $frontmatter.strings }}</div>

## Signature

```> encode (encoding) --ignore-errors```

## Parameters

 -  `encoding`: the text encoding to use
 -  `--ignore-errors` `(-i)`: when a character isn't in the given encoding, replace with a HTML entity (like `&#127880;`)

## Notes
Multiple encodings are supported; here are a few:
big5, euc-jp, euc-kr, gbk, iso-8859-1, cp1252, latin5

Note that since the Encoding Standard doesn't specify encoders for utf-16le and utf-16be, these are not yet supported.

For a more complete list of encodings, please refer to the encoding_rs
documentation link at https://docs.rs/encoding_rs/latest/encoding_rs/#statics
## Examples

Encode an UTF-8 string into Shift-JIS
```shell
> "負けると知って戦うのが、遥かに美しいのだ" | encode shift-jis
Length: 40 (0x28) bytes | printable whitespace ascii_other non_ascii
00000000:   95 89 82 af  82 e9 82 c6  92 6d 82 c1  82 c4 90 ed   ×××××××××m××××××
00000010:   82 a4 82 cc  82 aa 81 41  97 79 82 a9  82 c9 94 fc   ×××××××A×y××××××
00000020:   82 b5 82 a2  82 cc 82 be                             ××××××××

```

Replace characters with HTML entities if they can't be encoded
```shell
> "🎈" | encode -i shift-jis
Length: 9 (0x9) bytes | printable whitespace ascii_other non_ascii
00000000:   26 23 31 32  37 38 38 30  3b                         &#127880;

```
