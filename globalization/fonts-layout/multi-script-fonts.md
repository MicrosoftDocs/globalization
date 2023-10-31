---
title: Multi-script fonts
description: Some fonts are created with support for more than one script (writing system).
ms.date: 10/31/2023
author: jowilco
---
# Multi-script fonts

When supporting several scripts in a single document, application, or website, you typically want to have a consistent appearance. Many fonts contain just a limited number of glyphs and are only intended to support a single script. You might need to use several fonts to support all the glyphs that are needed in the text that you wish to display.

Fortunately, multi-script fonts are becoming more widespread. Fonts with support for Latin, Greek/Coptic, and Cyrillic are relatively common. Microsoft supplies several fonts that support multiple scripts with Windows. For example, Leelawadee UI supports Khmer, Lao, and Thai scripts and Nirmala UI supports several Indic scripts. Almost all fonts have at least limited support for Latin glyphs in addition to the scripts for which they are primarily designed.

One of the challenges with using a single font to support a broad range of scripts is the limit of 65,535 glyphs in an OpenType font file. OpenType fonts can be combined into OpenType Font Collections to support additional scripts; however, memory consumption and download size, when used as web fonts, impose practical limits on trying to support all glyphs irrespective of context.

Font collections are a good solution for supporting multiple scripts in documents, websites, and applications. Google’s Noto font collection includes over 2,000 fonts with coverage for over 150 scripts. These fonts can be combined to provide a unified appearance in your documents, applications, or websites. Rather than one very large font file, you can use only those fonts from the collection that support the glyphs that you are using, reducing file size or download time.

If you need to support text that contains glyphs from several scripts, [font fallback](/windows/win32/intl/using-font-fallback) is a good option. Rather than trying to identify a font that contains all the glyphs that you need, you can specify a set of fonts that can be used together. If a glyph is not available in the first font of the set, the renderer will try the subsequent fonts until a font is found that can display the glyph.
