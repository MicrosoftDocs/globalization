---
title: Browser encoding setting
description: It is recommended to use one of the Unicode encodings, but if you are working with legacy software you may need to continue to use older code pages.
ms.assetid: c2dd9e6d-6be7-4699-97ff-94cfe62fafff
---
# Browser encoding setting

It is recommended to use one of the Unicode encodings, but if you are working with legacy software you may need to continue to use older code pages.

A code page is a byte-oriented list of selected character codes in a certain order.
Code pages are usually defined to support a specific language or a specific group of languages that share common writing system.
The first 127 code points typically represent the same characters across code pages.
This common set is often called the "ASCII characters".
It is the upper 128 code points 128-255 (0-based) where code pages differ considerably.

For example, code page 1253 provides character codes required in the Greek writing system and code page 1252 provides the characters for Latin writing systems including English, German and French.
It is the upper 128 code points that contain either the accent characters or the Greek characters.
Thus you cannot store Greek and German in the same code stream unless you put some type of out-of-band identifier to indicate what code page you are referencing.

This becomes even more complex when dealing with Asian character sets.
Chinese, Japanese and Korean contain thousands of characters, a different scheme needed to be developed but it had to be based on the concept of byte-based code pages.
Thus Double Byte Character Sets (DBCS) and, more generally, Multi-Byte Character Sets (MBCS) were born.

In MBCS, each Asian character is represented by a sequence code points (thus double-byte or multi-byte).
For programming awareness, a set of points are set aside to represent the first byte of the set and are not valued unless they are immediately followed by a defined second byte.
MBCS meant that you had to write code that would treat these sequences of bytes as one unit.
This still disallowed combining different languages in the same data stream, because depending on the codepage, the same sequence of bytes may different characters for the different languages.

In order to allow for the storage of different languages in the same data stream, [Unicode](../encoding/encoding-overview.md) was created.
Unicode is able to represent all the world's languages with a single encoding.
The use of Unicode allows for easier creation of world-ready code, because it allows a single, simpler implementation that can handle world-wide text.