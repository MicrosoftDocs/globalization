---
title: Browser encoding setting
description: It is recommended to use one of the Unicode encodings, but if you are working with legacy software you may need to continue to use code pages.
ms.assetid: c2dd9e6d-6be7-4699-97ff-94cfe62fafff
---
# Browser encoding setting

It is recommended to use one of the Unicode encodings, but if you are working with legacy software or data you may need to continue to use code pages.

A code page is a byte-oriented list of selected character codes in a certain order.
Code pages are usually defined to support a specific language or a specific group of languages that share common writing system.
The first 127 byte values typically represent the same characters across code pages.
This common set is often called the "ASCII characters".
It is the upper 128 byte values 128-255 where code pages differ considerably.

For example, code page 1253 provides characters required in the Greek writing system and code page 1252 provides the characters for Latin writing systems including English, German and French.
It is the upper 128 code points that contain either the accent characters or the Greek characters.
Thus you cannot store Greek and German in the same code stream unless you put some type of out-of-band identifier to indicate what code page you are referencing.

This becomes even more complex when dealing with Asian character sets.
Chinese, Japanese and Korean contain thousands of characters, a different scheme needed to be developed.
Thus Double Byte Character Sets (DBCS) and, more generally, Multi-Byte Character Sets (MBCS) were born.

In these encodings, each non-ASCII character is represented by a sequence of one or more bytes (thus double-byte or multi-byte).
A set of values are defined to represent the first byte of a multi-byte sequence sequence (the lead byte) and are meaningless unless they are immediately followed by defined trailing bytes.
This means that you must write code that treats these sequences of bytes as a single unit.
However, each code page is unique, with different values for leading and trailing bytes.
When the wrong code page is used to interpret data, the result is garbage, and easily results in data loss.
This creates a very complex problem for applications and operating systems meant for global use.

A new, single encoding that can represent all the world's writing systems was needed, so [Unicode](../encoding/encoding-overview.md) was created.
Unicode allows for easier creation of world-ready code, because a single, simpler implementation can handle world-wide text.
