---
title: Customize font selection with font fallback and font linking
description: Customize font selection with font fallback and font linking for multi-language and multi-script applications in Windows and .NET framework.
ms.date: 10/31/2023
author: jowilco
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-seo-date:10/31/2023
  - ai-gen-desc
---

# Fonts

A critical requirement for any operating system that supports international users is the ability to enter, select, and display the glyphs used by the users’ writing systems (scripts). For example, developers need control over the fonts, font sizes, and font styles that are used in their applications. Document editing applications typically allow users to set the font, font size, and font style for the whole document or smaller fragments (for example, characters, words, sentences).

There are various font formats for use with computers, mobile devices, and other hardware such as printers. [OpenType](/typography/opentype/) and [TrueType](/typography/truetype/) are the most common font formats in use today. Older font formats, such as Adobe Type 1 (or PostScript Type 1) fonts can still be installed on Windows 10 and Windows 11, although many foundries have replaced Type 1 products with the equivalent OpenType or TrueType versions.

To support users around the world, text-display support for new scripts has been added in each major release of Windows. The number of [fonts distributed with each Windows release](font-support.md) has increased to meet the needs of the supported scripts.

Although users often have broad scope to change font, font size, and font style for their applications and documents, there's an expectation that users shouldn't need to select different fonts for text using different scripts before that text is displayed correctly:

- The user might not know which font is the most suitable choice.
- Simple applications such as Notepad only allow one font for the whole document.
- This level of font selection imposes productivity overhead.

Applications should endeavor to display glyphs correctly, irrespective of the script used. Displaying the correct glyph involves techniques like font fallback. For Windows, several text layout and glyph rendering systems, including [GDI](/windows/win32/gdi), [GDI+](/windows/win32/gdiplus), [Uniscribe](/windows/win32/intl/uniscribe), and [DirectWrite](/windows/win32/directwrite) are supported. In most cases, developers won't need to use these technologies directly as modern frameworks like .NET are designed to support multi-language and multi-script applications. However, knowledge of these glyph rendering systems and how font fallback and font linking can be used to customize font selection can be helpful in customizing font behavior.

## Font fallback

One benefit of Unicode is the ability to represent many languages without additional data specifying script. However, the broad glyph and script support in Unicode is also a problem, since few fonts support more than a few scripts. Indeed, it's difficult to do a good job of making fonts with glyphs for different scripts such that all conform to one set of vertical metrics. To overcome this limitation, and to accommodate complex scripts, most rendering systems (the technology for displaying the font onto the screen) include functionality to detect if the currently selected font doesn't support a particular script and can automatically switch (fall back) to a predefined font that has appropriate glyphs for the desired script. All these operations are transparent to the user.

Here's an example to better understand this mechanism. A user selects the Tahoma font to enter some text first in English, next in Hebrew, and then in Telugu. Tahoma provides support for Latin and Hebrew scripts but doesn't contain any Telugu glyphs. The application or the rendering system detects this lack of font support and automatically renders the Telugu script by using its fallback font. Each application and each operating system can define its own fallback font for any Unicode script range, depending on the technologies used.

The .NET framework supports font fallback via the [FontFamily](/dotnet/api/system.windows.media.fontfamily#font-fallback) class. There are three options for defining font fallback sequences in .NET:

1. [Specify the fallback sequence in code](/dotnet/api/system.windows.media.fontfamily#defining-a-font-fallback-sequence-in-code).
1. Use the default [composite fonts](/dotnet/api/system.windows.media.fontfamily#composite-fonts) that are specified as standard with the .NET framework installation.
1. Define your own composite font, using [FontFamilyMap](/dotnet/api/system.windows.media.fontfamilymap) to specify the set of Unicode code points, language, and target font family.

For Win32 and Uniscribe, use [ScriptShape](/windows/win32/api/usp10/nf-usp10-scriptshape) to determine whether glyphs are supported in a font to implement [font fallback](/windows/win32/intl/using-font-fallback).

CSS supports font fallback through the font-family property. You can specify one or more fonts to be used in order of precedence when displaying text. You should always end with one of the generic fonts (serif, sans-serif, monospace, cursive, fantasy) so that the browser is always able to display text if none of the specified fonts is available.

## Font linking and GDI

Font linking is a mechanism enabled within GDI and takes priority over font fallback. Unlike font fallback, in which the selected font is internally replaced by a predefined font, using font linking it's possible to link one or more fonts (called "linked fonts") to another font (called the "base font"). Once you link fonts, you can use the linked fonts to display code points that don't exist in the base font but do exist in one of the linked fonts. For example, linking a Hangeul font and a Japanese font to a Tahoma font allows you to display both Korean and Japanese characters while specifying Tahoma font. Font linking requires specifying the priority of the fonts to be linked together as though in a chain. A font later in the chain can only add glyphs to an earlier font; you can't override or replace glyphs in the early font.

Font linking isn't a substitute for choosing the right font in the first place. Rather, it can be used as a means of preventing the user from being forced to manually select a font and prevent user interface text from being displayed as a default glyph (called tofu).

The registry key `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\FontLink\SystemLink` specifies several composite fonts and their corresponding font files.

With font linking, the font size of the text is maintained. The newly applied font is the same specified size as the original font. For example, if an 8-point Tahoma font was selected to type English and now the user enters some Japanese text, an 8-point Meiryo font (depending on the linked fonts) will be automatically selected. The 8-point font size might not be the best choice for some scripts, since it can make them hard to read.
Font linking can apply logic to estimate an appropriate font size, but the mechanism must use metrics exposed by the font that might or might not actually match the way the font appears. Explicit scaling factors for linked fonts can be specified in font linking registry entries. Scaling factors are specified as a pair of positive integers. For instance, the value `MEIRYO.TTC,Meiryo,128,85` indicates that the scaling algorithm should apply the scaling factors 128 and 85 whenever the given base font is linked to the Meiryo font.

Note that GDI+ isn't able to parse the scaling factors. Therefore, for the predefined linked fonts specified in the Windows registry, references to fonts with scaling factors are repeated without the scaling factors. In GDI+, the first reference, with the scaling factors, will appear to be to an unrecognized font and will be ignored. In GDI, the second reference is treated as redundant and ignored.

## Font substitution

The Windows operating system allows for font substitution, but font substitution should be considered a last resort approach. Windows font substitution is set with the registry entries under the key `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\FontSubstitutes`. The registry entry of “Helvetica” with the value of “Arial,” for instance, indicates to substitute Helvetica font with Arial font; and the registry entry of “Arial,0” with the value of “Arial,161” will substitute Arial with ANSI_CHARSET to Arial with GREEK_CHARSET.

## Font guidelines

- Don't assume a selected font supports the desired script. For example, it's impossible to use Miriam (a Hebrew font) to display glyphs from the hiragana script.
- Don't hardcode font face names. These values might need to change based on the language of the user interface and should be defined as a table or matrix based on the required script.
- Understand your font fallback. For example, using CSS, you could define `font-family: Georgia, "Times New Roman", "Microsoft YaHei", 微软雅黑, STXihei, 华文细黑, serif;` which lists the Latin fonts first, includes both Microsoft and Apple fonts, and includes Chinese font names.
- Avoid having font names as part of localizable resources. If a translator translates the font name it might no longer match a supported font. Font choice should be part of the UI design and should be considered analogous to branding.
- Ensure that the font size is dynamic according to the script to be displayed. Some glyphs in small font sizes might not be legible, so font size needs to be adjusted based on the script.
- Don't assume a given font is installed. The user might delete or uninstall fonts (even a system font!).
- Be careful of using `@font-face` embedding, especially for mobile scenarios. Some fonts contain many glyphs and have a correspondingly large file size.
