---
title: Character exclusion
description: In certain languages such as Thai, specific character sequences are not allowed and should be filtered on input.
ms.date: 01/01/2022
---

# Character exclusion

Certain sequences of characters are not allowed in some languages and scripts.
Invalid sequences should be dropped if seen in the input stream.

The Unicode Normalization Algorithm establishes the process of excluding invalid sequences.
See [Unicode - Composition Exclusion](https://www.unicode.org/reports/tr15/#Primary_Exclusion_List_Table)

<!-- This content originally referred to Thai input sequence checking, but I find no mention of Thai in the Unicode Normalization info ->