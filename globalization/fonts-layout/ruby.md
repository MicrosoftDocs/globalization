---
title: Ruby characters and text annotation
description: Learn about using ruby characters with unfamiliar or multi-pronunciation characters.
ms.date: 10/31/2023
author: jowilco
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-desc
  - ai-seo-date:11/10/2023
---

# Ruby characters and text annotation

A ruby character is an annotative gloss placed above or to the right of characters to aid the user in pronunciation. Ruby characters are named after an original name of type with a height of 5.5. points. The terms phonetic guide, yomigana, furigana, or ruby are used interchangeably; however, the terms yomigana and furigana are only used in a Japanese context. Ruby characters are important for logographic languages where the reader might not be familiar with a character, or the character has more than one pronunciation.

The orientation of the ruby character matches the base characters. For horizontal writing, the ruby characters appear above the base characters. For vertical writing, the ruby characters typically appear to the right of the base characters.

Horizontal:
<iframe src="ruby_horizontal.html" width="100%" height="60px"></iframe>

Vertical:
<iframe src="ruby_vertical.html" width="100%" height="80px"></iframe>

Ruby characters are typically half the size of the corresponding base characters. If the base characters are using a very small font size, it's better to use other annotation methods, such as including the reading in parentheses after the base characters.

More information about ruby characters, and about Japanese text layout in general, can be found at https://www.w3.org/TR/jlreq.

## Rendering ruby characters

Text editors, like Microsoft Word, can have tools to facilitate adding ruby characters. In Microsoft Word, when you choose to add a phonetic guide, a default reading is given; however, the reading might not be correct in the context.

HTML supports ruby characters via the `<ruby>` element or via CSS. When you're using either method, you need to supply the reading for the base characters. If your text uses the `<ruby>` elements, you can use CSS to determine whether the ruby characters are displayed to the user.
