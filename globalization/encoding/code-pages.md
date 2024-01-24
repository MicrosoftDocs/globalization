---
title: Code pages
description: Understand the concept of code pages and how they support different languages and writing systems.
ms.date: 1/24/2024
author: jowilco
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-desc
  - ai-seo-date:01/24/2024
---

# Code pages

A code page is a list of selected character codes (characters represented as code points). Code pages were originally defined to support a specific language or groups of languages that share a common writing system. The original Windows code pages supported 8-bit Single Byte Character Sets (SBCS), composed of 256 characters. The first 127 code points of each code page typically represented the same "ASCII" characters. The upper 128 code points (values 128-255) of each code page differed considerably.

For example, code page 1253 provides character codes required in the Greek writing system and code page 1252 provides the characters to support languages such as English, German, and French that use the Latin writing system. It's the upper 128 code points that contain either the Greek characters or characters with diacritical marks. Using these 8-bit code pages, you can't store Greek and German in the same code stream unless you can also identify when text transitions from one encoding to the other.

To support writing systems for languages such as Chinese, Japanese, and Korean that use more than 256 characters, a different scheme needed to be developed to overcome the 256-character limit of SBCS. Double Byte Character Sets (DBCS) and, more generally, Multi-Byte Character Sets (MBCS) were developed to extend the SBCS design. Code page 932 is a variant of the Shift JIS Japanese character encoding. Code page 936 originally covered the GB 2312 character set for Simplified Chinese but was expanded to cover the GBX extension. In both character sets, the first 127 code points are reserved for ASCII characters, while the following 128 code points could also be characters or the lead byte of a multi-byte character. The character sets aren't interchangeable even if they contain many of the same characters. For example, the character 字 (U+5B57) is mapped to `0x8E 0x9A` in code page 932, but mapped to `0xD7 0xD6` in code page 936.

Most applications written today handle character data primarily as [Unicode](unicode-standard.md), using one of several encodings such as UTF-8 or UTF-16LE. Windows supports several of these encodings with code pages, for example, code page 65001 supports the UTF-8 encoding of Unicode.

While the current versions of Windows use Unicode internally, Windows still supports [many code pages](/windows/win32/intl/code-page-identifiers) for:

- communicating with legacy applications.
- communicating with older mail and news servers, which might not support Unicode.
- using command-line applications that don’t support Unicode.
