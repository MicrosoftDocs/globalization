---
title: Discover the features and benefits of OpenType fonts
description: Discover the benefits of OpenType fonts, including rich mapping for ligatures and positional forms, support for multiple languages, and cross-platform compatibility.
ms.date: 10/31/2023
author: jowilco
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-seo-date:10/31/2023
  - ai-gen-desc
---
# OpenType®

[OpenType](/typography/opentype/) is a font format developed jointly by Microsoft and Adobe as an extension of Apple’s TrueType font format. TrueType and OpenType fonts allow rich mapping between individual Unicode points and multiple glyphs, thus enabling support for ligatures, positional forms, alternates, and other substitutions. OpenType fonts can include information that supports two-dimensional glyph positioning and glyph attachment. OpenType fonts can also contain either TrueType or PostScript outlines. Layout features within OpenType fonts are organized by scripts (writing systems) and languages, allowing a single font to support multiple language variants, even within the writing system. A common implementation for this would provide alternatives for preferred stylistic differences based on culture, but it can also address complex issues such as character variants only used in the italic form in the Cyrillic alphabet.

Most commercially available fonts contain support for a single script and the basic Latin characters. The main reason behind the separation of scripts into separate font files relates to disk image size and, to a lesser extent, the performance overhead of loading a font that contains large numbers of glyphs.

OpenType has several distinctive features:

- The font encoding is based on Unicode and can support any script (or multiple scripts at once) to a maximum of 65,536 glyphs. Note that it's glyphs, not characters. Fonts with stylistic or rendering features such as ligatures or contextual alternates might have a 1-to-many mapping of Unicode code point to glyphs.
- OpenType also has data tables that allow proper typographic treatment of complex scripts, including positioning and morphing logic.
- OpenType fonts can be used on multiple platforms, including Windows, macOS, and Unix/Linus.

To learn more about OpenType fonts, refer to the most recent version of the [OpenType specification](/typography/opentype/spec/).
