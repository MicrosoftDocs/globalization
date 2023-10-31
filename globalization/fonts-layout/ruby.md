---
title: Ruby characters and text annotation
description: Some locales have specialized layout for text annotations and "ruby".
ms.date: 10/31/2023
author: jowilco
---

# Ruby characters and text annotation

A ruby character, named after an original name of type with a height of 5.5. points, is an annotative gloss placed above or to the right of characters to aid the user in pronunciation. The terms phonetic guide, yomigana, furigana, or ruby are used somewhat interchangeably; however, the terms yomigana and furigana are only used in a Japanese context. Ruby characters are particularly important for logographic languages where the reader may not be familiar with a character, or the character has more than one pronunciation.

The orientation of the ruby character will match the base characters. For horizontal writing, the ruby characters will appear above the base characters. For vertical writing, the ruby characters will typically appear to the right of the base characters.

<ruby>東京<rt>とうきょう</rt></ruby>

Ruby characters are typically half the size of the corresponding base characters, but if the base characters are using a very small font size, it is better to use other annotation methods, such as including the reading in parentheses after the base characters.

More information about ruby characters, and about Japanese text layout in general, can be found at https://www.w3.org/TR/jlreq.

## Rendering ruby characters

Text editors, like Microsoft Word, can have tools to facilitate adding ruby characters. In Microsoft Word, when you choose to add a phonetic guide, a default reading will be given; however, the reading might not be correct in the context.

HTML supports ruby characters via the `<ruby>` element or via CSS. Note that when you are using either method, you need to supply the reading for the base characters. If your text uses the `<ruby>` elements, you can use CSS to determine whether the ruby characters are displayed to the user.
