---
title: Complex scripts and shaping engines
description: The universal shaping engine combines an intimate knowledge of language scripts and the OpenType font format to provide sophisticated rendering of complex scripts.
ms.date: 10/31/2023
author: jowilco
---

# Complex scripts and shaping engines

*Complex script* refers to any writing system that has contextual and non-linear requirements to render their typography correctly. These requirements include:

- Ligatures, where two consecutive characters are combined into one shape (Latin, Devanagari)
- Reordering, where some characters are written before the letter they follow in pronunciation (Bengali, Sinhala, and other Indic scripts)
- Context-shaping, where some letters change shape depending on whether they occur in the beginning, middle, or the end of the word (Arabic, Mongolian)

It should be noted that such processing is not optional; it is essential to correctly render text in these scripts. Additional glyph processing to render appropriately sophisticated typography may be desirable beyond the minimum required to make the text readable.

[Uniscribe](/windows/win32/intl/using-uniscribe) is a set of Windows APIs and shaping engines that allow for a high degree of control for typography and for processing complex scripts. Each of the shaping engines in Uniscribe contains the shaping knowledge for a particular script or closely related group of scripts. This shaping knowledge focuses on the basic element of each script, which will vary depending on the nature of the writing system. In the Indic scripts, for example, the basic element that needs to be processed is the syllable; in the Arabic script the basic element is always a pair of letters, with the second letter of a pair becoming the first letter of the next. Uniscribe analyses and prepares strings of Unicode text by breaking runs (i.e., strings of text in a single script with uniform formatting) into clusters corresponding to the basic element for that script. The kind of character preprocessing that some complex scripts require (for example, reordering of certain characters in the string) are detailed in the Unicode Standard.

Uniscribe uses several script-specific shaping engines for handling typography in supported complex scripts, including [Arabic](/typography/script-development/arabic), [Buginese](/typography/script-development/buginese), [Korean (Hangul)](/typography/script-development/hangul), [Hebrew](/typography/script-development/hebrew), [Indic](/typography/script-development/bengali), [Javanese](/typography/script-development/javanese), [Khmer](/typography/script-development/khmer), [Lao](/typography/script-development/lao), [Myanmar](/typography/script-development/myanmar), [Sinhala](/typography/script-development/sinhala), [Syriac](/typography/script-development/syriac), [Thaana](/typography/script-development/thaana), [Thai](/typography/script-development/thai), and [Tibetan](/typography/script-development/tibetan). Uniscribe has two additional engines:

- [Standard shaping engine](/typography/script-development/standard) for use with any non-complex script (Latin, Cyrillic, Greek, etc.)
- [Universal Shaping Engine](/typography/script-development/use) (USE) for use with complex scripts that are not supported by one of the dedicated shaping engines. The following complex scripts included in the Unicode Standard 15.0 are supported in the Universal Shaping Engine: ADLaM, Ahom, Bhaiksuki, Balinese, Batak, Brahmi, Buginese, Buhid, Chakma, Cham, Chorasmian, Cypro Minoan, Dives Akuru, Dogra, Duployan, Egyptian Hieroglyphs, Elymaic, Grantha, Gunjala Gondi, Hanifi Rohingya, Hanunoo, Javanese, Kaithi, Kawi, Kayah Li, Kharoshthi, Khitan Small Script, Khojki, Khudawadi, Lepcha, Limbu, Mahajani, Makasar, Mandaic, Manichaean, Marchen, Masaram Gondi, Medefaidrin, Meitei Mayek, Miao, Modi, Mongolian, Multani, Nag Mundari, Nandinagari, Newa, N’Ko, Nyiakeng Puachue Hmong, Old Sogdian, Old Uyghur, Pahawh Hmong, Phags-pa, Psalter Pahlavi, Rejang, Saurashtra, Sharada, Siddham, Sinhala, Sogdian, Soyombo, Sundanese, Syloti Nagri, Tagalog, Tagbanwa, Tai Le, *Tai Tham, Tai Viet, Takri, Tangsa, Tibetan, Tifinagh, Tirhuta, Toto, Vithkuqi, Wancho, Yezidi, Zanabazar Square
