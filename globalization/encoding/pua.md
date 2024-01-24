---
title: Private use area (PUA) characters and End-user-defined characters (EUDCs)
description: Learn about Private Use Area (PUA) characters and how they can be defined and used by individuals and organizations to create custom characters.
ms.date: 1/24/2024
author: jowilco
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-desc
  - ai-seo-date:01/24/2024
---

# Private use area (PUA) characters and End-user-defined characters (EUDCs)

Private use area (PUA) characters in Unicode, or End-user-defined characters (EUDC) in double-byte character sets (DBCSs) are custom characters that can be defined by individuals and organizations, such as equipment manufacturers, user groups, government bodies, or font publishers. Their use enables users to form names and other words using characters that are not available in standard screen and printer fonts.

Unicode has three defined ranges for private-use characters.

- BMP: U+E000..U+F8FF
- Plane 15: U+F0000..U+FFFFD and U+100000..U+10FFFD
- Plane 16: U+F0000..U+FFFFD and U+100000..U+10FFFD

Since the same code points in the PUA can be defined by different individuals or organizations, you cannot assume that any given code point in the PUA will represent the same character for different implementations. Shared use of the PUA must be defined by “private agreement”; users of characters implemented in the PUA have a common understanding of the characters and their code points.

## PUA characters and fonts

Given that the characters are user defined, the same code point may have different meanings in different contexts. An end-user needs to have the appropriate font to display the character they are expecting. For example, many web designers create a symbol web font for site icons. These fonts may make use of the PUA ranges to encode their symbols.

To create a PUA character, select a character value within any of the desired ranges and add a glyph to a font that corresponds to that character value. Any Unicode font can contain PUA characters; however, your ability to add characters to a third-party font might be limited by the font’s license agreement.

A font is called a "separate" PUA font if it contains only PUA characters. A font is an "integrated" PUA font if it contains standard characters as well as PUA characters.

If you are distributing documents containing characters supported by the PUA, you will need to ensure that the recipients also have the font that supports the characters.
