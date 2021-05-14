---
title: Code pages
description: A code page is a list of selected characters represented as numeric values.
ms.date: 06/27/2016
---

# Code Pages

A code page, or character set, is a list of selected characters each with a corresponding numerical value. Historically, code pages have been defined to support specific languages or groups of languages that share common writing systems. The character set most commonly used in computers today is Unicode, a global standard for character encoding that currently supports 154 scripts via 143,859 distinct characters. Internally, Windows applications use the UTF-16 implementation of Unicode; however, some Windows applications must work with the older character sets that are native to Windows Me/98/95. Windows code pages allow your application to work with these character sets. These character sets can be divided into:

- Single-byte character sets (SBCS). In an SBCS, each character is identified by a value one byte wide.
- Multibyte character sets, in particular the double-byte character sets (DBCS).

In UTF-16, most characters are identified by two-byte codes. The less commonly used supplementary characters are each represented by a surrogate pair, which is a pair of two-byte codes. For more information, see Surrogates and Supplementary Characters.

### Single-byte Character Sets (SBCS)

A single-byte character set (SBCS) is a mapping of 256 individual characters to their identifying code values, implemented as a code page. For example, a SBCS can correspond to a Windows code page, an OEM code page, or an EBCDIC code page.

https://docs.microsoft.com/en-us/windows/win32/intl/code-page-identifiers

### Multi-byte Character Sets (MBCS)

#### Double-byte Character Sets (DBCS)























A code page is a list of selected character codes characters represented as code points) in a certain order. Code pages are usually defined to support specific languages or groups of languages that share common writing systems. All Windows code pages can only contain 256 code points. Most of the first 127 code points represent the same characters. This is to allow for continuity and legacy code. It is the upper 128 code points 128-255 (0-based) where code pages differ considerably.

For example, code page 1253 provides character codes required in the Greek writing system and code page 1252 provides the characters for Latin writing systems including English, German and French. It is the upper 128 code points that contain either the accent characters or the Greek characters. Thus you cannot store Greek and German in the same code stream unless you put some type of identifier to indicate what code page you are referencing.

This becomes even more complex when dealing with Asian character sets. Because Chinese, Japanese and Korean contain more than 256 characters, a different scheme needed to be developed but it had to be based on the concept of 256 character codepages. Thus Double Byte Character Sets (DBCS) were born.

Each Asian character is represented by a pair of code points (thus double-byte). For programming awareness, a set of points are set aside to represent the first byte of the set and are not valued unless they are immediately followed by a defined second byte. DBCS meant that you had to write code that would treat these pair of code points as one,and this still disallowed the combining of say Japanese and Chinese in the same data stream, because depending on the codepage the same double-byte code points represent different characters for the different languages.

In order to allow for the storage of different languages in the same data stream, [Unicode](encoding-overview.md) was created. This one "codepage" can represent over 64,000 characters and with surrogates it can represent over a million characters. The use of Unicode in Windows allows for easier creation of World-Ready code, because you no longer have to worry about which codepage you are addressing, nor whether you had to group character points to represent one character.

Please note that if still supporting Win95/98/ME applications, you will need to convert the Unicode code points back to Window codepages. This is because Win95/98/ME GDI is ANSI based. But this is made easy with the functions **WideChartoMultiByte** and **MultiByteToWideChar**. See "[Unicode and Character Sets](https://msdn.microsoft.com/library/dd374083.aspx)" on MSDN.

For information about encodings in web pages, please see [**MLang**](https://msdn.microsoft.com/library/aa767865.aspx) on MSDN.
