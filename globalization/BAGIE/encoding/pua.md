---
title: Private Use Area
description: The Private Use Area (PUA) may be used to display characters currently not in the Unicode standard. 
ms.date: 01/09/2019
---

# Private Use Area

Private Use Area (PUA) characters in Unicode, and End-User-Defined Characters (EUDC) in double-byte character sets (DBCSs), are custom characters. They can be defined and implemented by, for example, an equipment manufacturer, a user group, a government body, or a font design company. Custom characters enables users to form names and other words using characters that are not available in standard screen and printer fonts.

Unicode has three defined ranges that are not assigned any particular character but instead may be used by individuals and organizations.
U+E000 to U+F8FF, U+F0000 to U+FFFFD, and U+100000 to U+10FFFD {JRW - verify this}

Given that the characters are user defined, the same code point may have different meanings in different contexts. An end-user needs to have the appropriate font to display the character they are expecting. For example, many web designers create a symbol webfont for site icons. These fonts may make use of the PUA ranges.

## Related Content
* [Private-Use Characters, Noncharacters & Sentinels FAQ](http://www.unicode.org/faq/private_use.html)
