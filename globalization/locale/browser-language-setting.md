---
title: Browser Language Setting
description: 
ms.assetid: c2dd9e6d-6be7-4699-97ff-94cfe62fafff
ms.date: 
---
# Code Pages

It is recommended to use one of the Unicode encodings, but if you are working with legacy software you may need to continue to use older code pages.

A code page is a list of selected character codes characters represented as code points) in a certain order. Code pages are usually defined to support specific languages or groups of languages that share common writing systems. All Window code pages can only contain 256 code points. Most of the first 127 code points represent the same characters. This is to allow for continuity and legacy code. It is the upper 128 code points 128-255 (0-based) where code pages differ considerably.

For example, code page 1253 provides character codes required in the Greek writing system and code page 1252 provides the characters for Latin writing systems including English, German and French. It is the upper 128 code points that contain either the accent characters or the Greek characters. Thus you cannot store Greek and German in the same code stream unless you put some type of identifier to indicate what code page you are referencing.

This becomes even more complex when dealing with Asian character sets. Because Chinese, Japanese and Korean contain more than 256 characters, a different scheme needed to be developed but it had to be based on the concept of 256 character codepages. Thus Double Byte Character Sets (DBCS) were born.

Each Asian character is represented by a pair of code points (thus double-byte). For programming awareness, a set of points are set aside to represent the first byte of the set and are not valued unless they are immediately followed by a defined second byte. DBCS meant that you had to write code that would treat these pair of code points as one,and this still disallowed the combining of say Japanese and Chinese in the same data stream, because depending on the codepage the same double-byte code points represent different characters for the different languages.

In order to allow for the storage of different languages in the same data stream, [[Unicode]](https://msdn.microsoft.com/en-us/globalization/mt683841) was created. This one "codepage" can represent over 64,000 characters and with surrogates it can represent over a million characters. The use of Unicode in Windows allows for easier creation of World-Ready code, because you no longer have to worry about which codepage you are addressing, nor whether you had to group character points to represent one character.

Please note that if still supporting Win95/98/ME applications, you will need to convert the Unicode code points back to Window codepages. This is because Win95/98/ME GDI is ANSI based. But this is made easy with the functions **WideChartoMultiByte** and **MultiByteToWideChar**. See "[[Unicode and Character Sets]](https://msdn.microsoft.com/en-us/library/dd374083.aspx)" on MSDN.

For information about encodings in web pages, please see [**[MLang]**](https://msdn.microsoft.com/en-us/library/aa767865.aspx) on MSDN.


