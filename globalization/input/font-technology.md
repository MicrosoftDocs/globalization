---
title: Font Technology
description: To select and display the right character or glyph is a big challenge in enabling the software to handle international character sets.
ms.assetid: 7ca05e14-0371-43bc-907e-204dc814d6eb
ms.date: 11/22/2016
---
# Font Technology

A critical requirement for any operating system that supports for international writing systems is the ability to enter, select, and display the right character. For most operating systems, this is elegantly handled though mobile devices may have restricted writing system coverage based on market release.

In addition to support for character coverage, when editing a multilingual document, the user has an expectation that they would not need to select a different font for each one of the scripts he or she wants to view because:

-   The average user might not know which font is the most suitable choice.
-   Simple applications such as Notepad.exe only allow one font for the whole document.
-   This type of font selection would impose a big productivity overhead.

Therefore, in addition to the font association technique used since the early versions of Windows, new features—font fallback, and font linking—were introduced to solve these types of font-selection problems. In additional, advances in font formats allow for more elegant solutions across writing systems.

### OpenType Fonts

The OpenType font format has been developed jointly by Microsoft and Adobe; it extends the TrueType font file format originally designed by Apple and Microsoft. TrueType and OpenType fonts allow rich mapping between individual Unicode points and multiple glyphs, thus enabling support for ligatures, positional forms, alternates, and other substitutions. OpenType fonts can also include information that supports two-dimensional glyph positioning and glyph attachment, and can contain either TrueType or PostScript outlines. Layout features within OpenType fonts are organized by scripts (writing systems) and languages, allowing a single font to support multiple language variants, even within the writing system. A common implementation for this would alternatives for preferred stylistic differences based on culture but it can also address complex issues such as the five character variants in the Cyrillic alphabet only used in the italic form.

Starting with Windows Vista, the Windows core fonts contain support for most of the world’s writing systems including Latin, Hebrew, Arabic, Greek, Cyrillic, Thai, and each of the East Asian scripts. However, no single font contains all of these writing systems; most contain a single script and the basic Latin characters. The main reason behind the separations of scripts into separate font files relates to disk image size contains and, to a less extent, the performance overhead loading a font that contains all of the worldwide glyphs. That’s particular a factor relative to the Chinese writing systems with each having more than 20,000 characters in the basic fonts.

OpenType has several distinctive features:

-   the font encoding is based on Unicode and can support any script (or multiple scripts at once) to a maximum of 65,536 glyphs. Note that is glyphs so fonts with stylistic features such as ligatures or contextual alternates may have a 1-to-many mapping of Unicode code point to glyphs.
-   OpenType also has data tables that allow proper typographic treatment of complex scripts, including positioning and morphing logic.
-   OpenType also has data tables that allow proper typographic treatment of complex scripts, including positioning and morphing logic.

### Font Fallback

One benefit of Unicode is the ability to represent many languages without additional data specifying writing system (script) requirements. This is also a problem, since very few fonts support more than a couple of scripts. Indeed, it's very difficult to do a good job of making fonts with glyphs for different scripts such that all conform to one set of vertical metrics. To overcome this limitation, and in order to accommodate complex scripts, most rendering systems (the technology for displaying the font onto the screen) include functionality to detect if the currently selected font doesn't support a particular script and can automatically switch—or fall back—to a predefined font that has appropriate glyphs for the desired script. All these operations are transparent to the user.

Here is an example to better understand this mechanism. A user selects the Tahoma font to enter some text first in English, next in Hebrew, and then in Telugu. Tahoma provides support for Latin and Hebrew scripts but does not contain any Telugu glyphs. The application or the rendering system detects this lack of font support and automatically renders the Telugu script by using its fallback font.

Each application and each operating system can define its own fallback font for any Unicode script range. Microsoft makes an effort ensure consistency across its application and products and includes an API (since Windows 8) to provide preferred font fallback recommendations to applications.

### Font Linking

Unlike font fallback, in which the selected font is internally replaced by a predefined font, in font linking (also called “composite fonts”) it is possible to link one or more fonts (called "linked fonts") to another font (called the "base font"). Once you link fonts, you can use the base font to display code points that do not exist in the base font, but that do exist in one of the linked fonts. For example, linking a Hangeul font and a Japanese font to a Tahoma font allows you to display both Korean and Japanese characters while specifying Tahoma font. The Noto family of fonts uses the model to create what appears as a single font by combing script-specific font files.

**Note:** Font linking requires specifying the priority of the fonts in linked together as though in a change. A font later in the chain can only add glyphs to an earlier font; you cannot override or replace glyphs in the early font.

If font linking is enabled on your device, you can examine the registry by enumerating the subkeys of the registry key at HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\FontLink\\SystemLink to determine the mappings of linked fonts to base fonts. You can add links by using Regedit to create additional subkeys. Once you have located the registry key that has just been mentioned, from the Edit menu, highlight the font face name of the font you want to link to and then from the Edit menu and click Modify. On a new line in the dialog field "Value data" of the Edit Multi-String dialog box, enter the path and file name to link to, and face name of the font. Use coma to separate the font file name and font face name.

**Caution:** Editing/modifying the font link entries in the Registry can be done, but is NOT supported by Microsoft. The wrong font link entry can leave the system unstable and impacts machine performance.

**Note:** After using Regedit to add the font linking, you have to log off Windows and log back on in order to have the new added font linking taking the effect.

**Important:** Font linking is a mechanism enabled within GDI and takes priority over font fallback.

With font fallback and font linking, the font size of the text is maintained. So the newly applied font will be the same specified size as that of the original font. For example, if an 8-point Tahoma font was selected to type English and now the user enters some Japanese text, an 8-point Meiryo font will be automatically selected. The 8-point font size might not be the best choice for some scripts, since it can make them hard to read.

Both font fallback and font linking can leverage logic to estimate an appropriate font size, but both mechanisms have to use metrics exposed by the font that might or might not actually match the way the font appears. Consider the difference in the visual height of English letters among 8-point Microsoft Sans Serif, 8-point Traditional Arabic, and 8-point Leelawadee UI:

| Microsoft Sans Serif | Traditional Arabic | Leelawadee  |
|:---:|:---:|:---:|
| E                    |  E                 |   E         |

Even though all of these are supposedly 8-point fonts, the apparent size of the English letters varies widely. Font fallback and font linking are no substitutes for choosing the right font in the first place. Rather, these mechanisms are simply a means of preventing the user from manually selecting a font; additionally, they prevent UI text from being displayed as a default glyph.

Even so, when font linking occurs, the system will attempt scale the linked font with the aim of making the glyphs from the linked font appear to match in size the glyphs from the base font. In previous versions the scaling algorithm was found not to give satisfactory results in all scenarios; in particular, it did not give good results when linking to new East Asian fonts that have no embedded bitmaps. To resolve this problem, an alternate scaling mechanism was introduced: explicit scaling factors for particular linked fonts could be specified in font linking registry entries. Scaling factors are specified as a pair of positive integers. For instance, the value
```
MEIRYO.TTC,Meiryo,128,85
```
indicates that the scaling algorithm should apply the scaling factors 128 and 85 whenever the given base font is linked to the Meiryo font.

Note that [GDI+](https://msdn.microsoft.com/en-us/library/ms533798(vs.85).aspx) is not able to parse these scaling factors. Thus, references to fonts with scaling factors are repeated without these scaling factors. In GDI+, the first reference, with the scaling factors, will appear to be to an unrecognized font and will be ignored. In GDI, the second reference will be treated as redundant and ignored.

### Font Substitution

Font substitution is implemented by an application to replace a request for a font that is not available into one that is available. In general, applications use PANOSE information (a set of numeric values summarizing the font’s style) to find the most appropriate matching font.

The Windows operating system also allows enabling font substitution but this should be considered a last resort approach. Windows substitution logic is also sensitive to charsets, so that a request for Arial with Western charset (0) can be translated into a request for Arial with Greek charset (161), for instance. Windows font substitution is set with the registry entries under the key HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\FontSubstitutes. The registry entry of “Helvetica” with the value of “Arial”, for instance, indicates to substitute Helvetica font with Arial font; and the registry entry of “Arial,0” with the value of “Arial,161” will substitute Arial with ANSI\_CHAERSET to Arial with GREEK\_CHARSET.

### Font Guidelines

1.  **Do not assume a selected font supports the desired script.** For example, it is impossible to use Miriam (a Hebrew font) to represent the hiragana script.
2.  **Do not hardcode font face names.** These values may need to change based on the language of the UI and should be defined as a table or matrix based on the required script.
3.  **Understand your font fallback.** Define to meet your design goals. For example, using HTML formats, you could define font-family: Georgia, "Times New Roman", "Microsoft YaHei", 微软雅黑, STXihei, 华文细黑, serif; which lists the Latin fonts first, includes both Microsoft and Apple fonts, and includes Chinese font names. For other coding solutions, the similar logic will be in a table or matrix.
4.  **Do not allow localization of font face names.** The values are part of the core design experience for a product and should be set as part of the coding developer rather than made accessible by a translator.
5.  **Do not hardcode the font size that you use**, and make sure that you make this variable customizable according to the script to be displayed; since some scripts are more complicated than others, they need more pixels to be displayed properly. The most reasonable way to think about this is font size (which is actually not consistently defined across writing systems) but the details rely actually upon the grid of available pixels for rendering. For example, most English characters can be displayed on a 5x7 grid, but Japanese characters need a grid of at least 16x16 to be seen clearly. Chinese characters, on the other hand, need a 24x24 grid. Thai characters only need 8 pixels for width, but they need at least 22 pixels for height. Thus it is easy to understand why some characters in a small font size might not be legible.
6.  **Do not assume a given font is installed.** The user might delete or uninstall fonts (even a system font!).
7.  **Beware @font-face embedding due to mobile scenarios.** This is particularly problematic for scripts with large numbers of glyphs.

## Related Content

-   [Script and Font Support in Windows](https://msdn.microsoft.com/en-us/globalization/mt791278)


