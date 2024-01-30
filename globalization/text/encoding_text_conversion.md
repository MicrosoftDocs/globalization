---
title: Encoding and text conversion
description: Use Unicode for storing and manipulating text to support a broad range of writing systems and avoid issues with code pages.
ms.date: 1/24/2024
author: jowilco
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-desc
  - ai-seo-date:01/24/2024
---
# Encoding and text conversion

Strings in libraries like ICU, frameworks like .NET, and programming languages like Java represent text as a series of [Unicode](../encoding/unicode-standard.md) characters. As Unicode supports a broad range of writing systems, it avoids one of the issues when working with [code pages](../encoding/code-pages.md) designed for a smaller set of languages. For example, code pages like Windows-1252 are designed for use with languages that use the Latin script. Japanese characters, such as Kanji or Hiragana aren’t supported in Windows-1252, so you wouldn’t be able to use Japanese text in a text file [encoded](../encoding/encoding-overview.md) as or a database column with a collation of Windows-1252.

Best practice is to use Unicode when storing or manipulating text. However, you might also need to support legacy systems that use different encodings or code pages. In this case, to minimize issues:

- Convert incoming data sources to Unicode as early as possible.
- Convert Unicode text to the target encoding as late as possible.
- When converting to Unicode or converting to the required encoding, validate that all characters are supported in the target encoding (lossless conversion). You'll also need to determine the appropriate fallback behavior when characters can't be converted from one encoding to another.

## Encoding detection

An additional challenge when working with multiple encodings or code pages is handling incoming data encoded with an unknown encoding. There are heuristic methods of guessing the encoding; however, these methods can be unreliable, especially for small amounts of data.

Unicode, and Unicode’s character encoding schemes, can facilitate encoding detection. UTF-8 defines valid and invalid byte sequences, so detecting an invalid byte sequence would mean that the encoding isn't UTF-8. For UTF-16, if you expect most or all of the characters in a stream are Latin characters, you would expect a large number of even or odd null bytes, depending on whether big-endian or little endian encoding is used.
