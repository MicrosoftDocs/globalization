---
title: Overlay Text Properties
description: 
ms.assetid: b655122c-41ec-4408-bdd2-f4965044b5a2
ms.date: 04/21/2017
---
# Overlay Text Properties

The remaining category of advanced text properties relates to text overlay. These properties apply not just to the glyph, but to an entire text string.

## Phonetic Guides, Yomi, Furigana, or "Ruby" Text

The terms phonetic guide, *yomi*, *furigana*, or “ruby” are used somewhat interchangeably to refer to an annotative gloss placed above or to the right of characters to aid the user in pronunciation. (Although *yomi* and *furigana* are only used in a Japanese context.) This is particularly important for logographic languages where the reader may not be familiar with the character or the character has more than one pronunciation.

![The word “Tokyo” with phonetic spelling](https://i-msdn.sec.s-msft.com/dynimg/IC868528.png "The word “Tokyo” with phonetic spelling")  ![The word “Tokyo” with phonetic spelling](https://i-msdn.sec.s-msft.com/dynimg/IC868530.png "The word “Tokyo” with phonetic spelling") 
**Figure 1:** The word “Tokyo” with phonetic spelling

The Worldwide Web Consortium [defines three levels of ruby support](https://www.w3.org/TR/jlreq/): mono ruby, group ruby, and jukugo ruby.

## Emphasizing Text

Due to the nature of the characters used by the East Asian languages, bolding often makes the characters unreadable. Therefore, emphasis points are used to emphasize certain text. Note that Simplified Chinese differs in that the emphasis mark is to the left of or below the text, instead of to the right or above the character.

Other methods to emphasis text include underlining (or "side line" if the text is written vertically) and the use of brackets (〈〉《》「」『』【】〔〕〖〗〘〙〚〛). Brackets may be used both vertically and horizontally.

Emphasis mark are not supported in HTML. Attempting to save documents containing emphasis marks may result in conversion to underline for the alternative "emphasizing" effect, instead.

![Emphasis marks on horizontal text](https://i-msdn.sec.s-msft.com/dynimg/IC868529.png "Emphasis marks on horizontal text") 

**Figure 2:** Emphasis marks on horizontal text.

![Emphasis marks on vertical text](https://i-msdn.sec.s-msft.com/dynimg/IC868532.png "Emphasis marks on vertical text") 

**Figure 3:** Emphasis marks on vertical text.

## Enclosed Characters

Enclosed characters are characters surrounded by equilateral shapes such as triangle, square, diamond or circle - commonly used in East Asia to indicate symbols. Enclosed characters are not supported in HTML; attempting to save documents with enclosed characters may result in removing the enclosing effects and leaving the base character.

![Example of enclosed characters](https://i-msdn.sec.s-msft.com/dynimg/IC868531.jpg "Example of enclosed characters") 

**Figure 4:** Example of enclosed characters
