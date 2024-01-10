---
title: Code pages
description: A codepage is a list of selected character codes characters represented as code points in a certain order.
ms.assetid: ecf7501a-f06a-423f-b263-2d472f3ed2a7
ms.date: 06/27/2016
---

# Code pages

It is recommended to use one of the Unicode encodings, but if you are working with legacy software you may need to continue to support code pages.

A code page is a list of selected character codes (characters represented as code points) in a certain order, such that each character is identified by a single number.
A code page is usually defined to support a specific language or groups of languages that share a common writing system.
In most code pages, the first 127 code points represent the same characters as defined in the "ASCII" character set; this is to allow for continuity and legacy data.
It is usually in the upper 128 code points (values 128–255) that code pages differ considerably.

For example, [code page 1253](https://en.wikipedia.org/wiki/Windows-1253) provides characters that are used in the Greek writing system and [code page 1252](https://en.wikipedia.org/wiki/Windows-1252) provides the characters for Latin writing systems including English, German and French.
In both of these code pages, it is the upper 128 code points that contain either accented or Greek characters.
Note that you cannot store Greek and German in the same code stream unless you include some type of identifier separate from the text to indicate which code page to use.

This problem becomes even more complex when dealing with Asian character sets: Chinese, Japanese and Korean contain more than 256 characters, so a different scheme needed to be developed but it had to be based on the concept of byte-based code pages. Thus Double Byte Character Sets (DBCS) and, more generally, Multi-Byte Character Sets (MBCS) were born.

In a DBCS or MBCS, many characters are represented by a pair of bytes (thus double-byte) or a sequence of 3 or more bytes.
For programming awareness, a set of points are set aside to represent the first byte of the set and are not valid unless they are immediately followed by a defined second (or third) byte in a specific range. This meant that you had to write code that would treat these varying-length sequences of bytes as one character.
This scheme still doesn't allow for the combining of Japanese and Chinese in the same data stream, because depending on the code page, the same code points represent different characters for the different languages.

In order to allow for the storage of different languages in the same data stream, [Unicode](encoding-overview.md) was created. Unicode can potentially support a total of 1,112,064 characters, of which 149,186 are currently defined (as of [Unicode 15.0, released 22 September 2022](https://www.unicode.org/versions/Unicode15.0.0/)).
The use of Unicode allows for easier creation of world-ready code, because you no longer have to worry about which code page you are addressing, nor whether you have to group character points to represent one character.
