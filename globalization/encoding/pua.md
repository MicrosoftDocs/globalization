---
title: Private Use Area
description: The Private Use Area (PUA) may be used to display characters currently not in the Unicode standard. 
ms.date: 01/09/2019
---

# Private Use Area (PUA)

Unicode has three defined ranges that are not assigned any particular character but instead may be used by individuals and organizations.
As long as there is agreement between parties, then the Private Use Area (PUA) may be used to display characters currently not in the Unicode standard.
Private-use characters are sometimes also referred to as [End User-Defined Characters](/windows/desktop/intl/eudc-registry-entries) (EUDC) or vendor-defined characters (VDC).

Given that the characters are user defined, the same code point may have different meanings in different contexts.
An end-user needs to have the appropriate font to display the character they are expecting.
For example, many web designers create a symbol web font for site icons.
These fonts may make use of the PUA ranges to encode their symbols.

Conversely, if a user or an application installs a font that has characters defined in the PUA there may be unexpected results.
Some of the definitions are documented — others are not.

It is not recommended to use PUA characters provided by the operating system or platform to avoid conflicts with the usage of certain individuals and organizations.

## Related Content

- [Private-Use Characters, Noncharacters & Sentinels FAQ](http://www.unicode.org/faq/private_use.html)
