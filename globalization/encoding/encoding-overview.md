---
title: Character and data encoding
description: Discover how character sets and code pages enable computers to represent and store characters used in writing systems.
ms.date: 1/24/2024
author: jowilco
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-desc
  - ai-seo-date:01/24/2024
---

# Character and data encoding

Most modern computers work with and store binary numbers in groups of 8 bits. These computers have no intrinsic knowledge of characters used in [writing systems](../fonts-layout/writing-systems.md). To represent and store the characters used in writing systems, computers use *character sets* that are mappings of characters to numerical values. The process of assigning characters to numerical values is called *character encoding*.

While there are many character encoding standards, one of the first in common use was ASCII (American Standard Code for Information Interchange). The original ASCII standard used a 7-bit character encoding system, representing 128 unique characters. Early Windows versions use an 8-bit character encoding system. These versions of Windows support multiple 8-bit [code pages](code-pages.md), enabling Windows releases in several languages.

To maintain compatibility with ASCII and to support a limited compatibility between 8-bit character sets, the first 127 characters of many code pages represent the ASCII characters. It's usually the upper 128 code points (values 128-255) where 8-bit code pages differ considerably. 8-bit character sets are commonly termed single-byte character sets (SBCS). SBCS and their corresponding code pages allowed support for a broad range of scripts and languages, including Cyrillic, Greek, Arabic, and Vietnamese.

Writing systems for languages such as Chinese, Japanese, and Korean use more than 256 characters, so a different scheme needed to be developed to overcome the 256-character limit of SBCS. Double Byte Character Sets (DBCS) and, more generally, Multi-Byte Character Sets (MBCS) were developed to extend the SBCS design. In a DBCS or an MBCS, many characters are represented by a pair of bytes (thus double-byte) or a sequence of 3 or more bytes. For programming awareness, a set of points are set aside to represent the first byte of the set and aren't valued unless they're immediately followed by a defined second (or third) byte in a specific range. When working with MBCS, you have to write code that treats these varying-length sequences of bytes as one character. This scheme still doesn't necessarily allow for the combining of Japanese and Chinese in the same data stream, because depending on the code page, the same code points could represent different characters for the different languages.

To allow for the storage of characters that support different writing systems in the same data stream, [Unicode](unicode-standard.md) was created. Unicode can represent over 64,000 characters, and with surrogates it can represent over a million characters. Using Unicode allows for easier creation of world-ready code because you don’t have to worry about which code page you're addressing, or whether you have to group character points to represent one character.

While Unicode-encoded data streams are common, you shouldn't assume that all data streams are encoded using the Unicode standard. When you're working with .NET, Java, and similar frameworks and languages, it's best practice to:

1. transform incoming data from any non-Unicode encoding to Unicode
1. process the data as Unicode
1. convert back to the original encoding as necessary on output
