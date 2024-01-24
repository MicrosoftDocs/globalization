---
title: Script and font support in Windows
description: Discover the changes made to script and font support for major releases of Windows.
author: pallep
ms.date: 8/10/2023
---

# Script and font support in Windows

Since before Windows 2000, text-display support for new scripts has been added in each major release of Windows. This article describes changes made in each major release.

Support for a script might require certain changes to text stack components and changes to fonts. The Windows operating system has many text stack components: DirectWrite, GDI, Uniscribe, GDI+, WPF, RichEdit, ComCtl32, and others. The information provided here pertains primarily to GDI and DirectWrite. It's also applicable to user interface frameworks such as RichEdit or the MSHTML rendering agent used for Windows apps and for rendering Web content, though those components might exhibit certain differences.

A detailed library of Microsoft fonts is available as part of the [Microsoft Typography](/typography/font-list/) documentation.

Comments on language usage are included in cases in which associations between scripts and languages might not be well known. The list of languages for any given script isn't necessarily exhaustive.

## Windows 11

The list of fonts included with Windows 11 is available in the [Windows 11 font list](/typography/fonts/windows_11_font_list).

Segoe UI Variable is the new system font for Windows. It's a refreshed take on the classic Segoe and uses variable font technology to dynamically provide great legibility at small sizes, and improved outlines at display sizes. Windows 11 also introduces a new system icon font, [Segoe Fluent Icons](/windows/apps/design/style/segoe-fluent-icons-font). This icon font aligns to the Fluent Design system. For more information about Windows 11 design principles, see [Typography in Windows 11](/windows/apps/design/signature-experiences/typography) and [Iconography in Windows 11](/windows/apps/design/signature-experiences/iconography).

The following table lists scripts newly supported in Windows 10, and associated fonts:

| New scripts | Region where script is from | Fonts | Comments on language usage |
| ----------- | --------------------------- | ----- | -------------------------- |
| Aegean Numbers                 | Europe                | Sans Serif Collection | Aegean numerals and punctuation |
| Ahom                           | Indian subcontinent   | Sans Serif Collection | Ahom |
| Ancient Greek Musical Notation | Europe                | Sans Serif Collection | Musical notation used in ancient Greece |
| Avestan                        | Middle East           | Sans Serif Collection | Avestan, Middle Persian |
| Balinese                       | Southeast Asia        | Sans Serif Collection | Balinese, Sasak |
| Bamum                          | Africa                | Ebrima                | Bamum |
| Bamum Supplement               | Africa                | Segoe UI Historic     | Bamum - Historic stage A-F of the Bamum script |
| Batak                          | Southeast Asia        | Sans Serif Collection | Alas-Kluet, Angkola, Karo, Mandailing, Pakpak, Simalungun, Toba |
| Buhid                          | Southeast Asia        | Sans Serif Collection | Buhid, Tagalog |
| Byzantine Musical Symbols      | Europe                | Sans Serif Collection | Musical notation for Byzantine music |
| Caucasian Albanian             | Europe                | Sans Serif Collection | Caucasian Albanian |
| Chakma                         | Indian subcontinent   | Nirmala UI            | Chakma   |
| Cham                           | Southeast Asia        | Sans Serif Collection | Cham, Sanskrit |
| Combining Half Marks           |                       | Sans Serif Collection | Diacritical marks spanning two or more characters |
| Common Indic Number Forms      | Indian subcontinent   | Sans Serif Collection | Representing fractions |
| Dogra                          | Indian subcontinent   | Sans Serif Collection | Dogri |
| Elbasan                        | Europe                | Sans Serif Collection | Albanian |
| Elymaic                        | Middle East           | Sans Serif Collection | Aramaic |
| Hanifi Rohingya                | Southeast Asia        | Sans Serif Collection | Rohingya |
| Hanunoo                        | Southeast Asia        | Sans Serif Collection | Hanunó'o, Tagalog |
| Kaithi                         | Indian subcontinent   | Sans Serif Collection | Awadhi, Bhojpuri, Hindustani, Magahi, Maithili, Nagpuri |
| Kayah Li                       | Southeast Asia        | Sans Serif Collection | Karenni |
| Khojki                         | Indian subcontinent   | Sans Serif Collection | Kutchi, Sindhi |
| Khudawadi                      | Indian subcontinent   | Sans Serif Collection | Sindhi |
| Lepcha                         | Indian subcontinent   | Sans Serif Collection | Lepcha |
| Limbu                          | Indian subcontinent   | Sans Serif Collection | Limbu |
| Linear A                       | Europe                | Sans Serif Collection | Unknown |
| Linear B Ideograms             | Europe                | Sans Serif Collection | Unknown |
| Linear B Syllabary             | Europe                | Sans Serif Collection | Mycenaean Greek |
| Mahajani                       | Indian subcontinent   | Sans Serif Collection | Hindi, Marwari, Punjabi |
| Mandaic                        | Middle East           | Sans Serif Collection | Mandaic |
| Manichaean                     | Central Asia          | Sans Serif Collection | Multiple Middle Iranian and Tocharian languages |
| Masaram Gondi                  | Indian subcontinent   | Sans Serif Collection | Gondi |
| Mayan Numerals                 | Mesoamerica           | Sans Serif Collection | Historical Mayan numeral system |
| Medefaidrin                    | Africa                | Sans Serif Collection | Medefaidrin |
| Mende Kikakui                  | Africa                | Sans Serif Collection | Mende |
| Miao                           | China, Southeast Asia | Sans Serif Collection | A-Hmao, Lipo, Nasu, Sichuan Miao |
| Modi                           | Indian subcontinent   | Sans Serif Collection | Marathi |
| Mro                            | Indian subcontinent   | Sans Serif Collection | Mru |
| Multani                        | Indian subcontinent   | Sans Serif Collection | Saraiki |
| Musical Symbols                |                       | Sans Serif Collection | Modern musical notation |
| Nabataean                      | Middle East           | Sans Serif Collection | Nabataean |
| Nyiakeng Puachue Hmong         | Southeast Asia        | Sans Serif Collection | White Hmong, Green Hmong |
| Old Hungarian                  | Europe                | Sans Serif Collection | Hungarian |
| Old North Arabian              | Middle East           | Sans Serif Collection | Ancient North Arabian |
| Old Sogdian                    | Central Asia          | Sans Serif Collection | Sogdian |
| Palmyrene                      | Middle East           | Sans Serif Collection | Palmyrene Aramaic |
| Pau Cin Hau                    | Southeast Asia        | Sans Serif Collection | Tedim |
| Psalter Pahlavi                | Middle East           | Sans Serif Collection | Middle Persian |
| Samaritan                      | Middle East           | Sans Serif Collection | Samaritan Aramaic, Samaritan Hebrew |
| Saurashtra                     | Indian subcontinent   | Sans Serif Collection | Saurashtra |
| Sharada                        | Indian subcontinent   | Sans Serif Collection | Kashmiri, Sanskrit |
| Sogdian                        | Central Asia          | Sans Serif Collection | Sogdian |
| Soyombo                        | Central Asia          | Sans Serif Collection | Mongolian, Sanskrit, Tibetan |
| Sundanese                      | Southeast Asia        | Sans Serif Collection | Sundanese |
| Sundanese Supplement           | Southeast Asia        | Sans Serif Collection | Sundanese |
| Takri                          | Indian subcontinent   | Sans Serif Collection | Western and Central Pahari languages |
| Tirhuta                        | Indian subcontinent   | Sans Serif Collection | Maithili, Sanskrit |
| Wancho                         | Indian subcontinent   | Sans Serif Collection | Wancho |
| Warang Citi                    | Indian subcontinent   | Sans Serif Collection | Ho |
| Zanabazar Square               | Central Asia          | Sans Serif Collection | Mongolian, Sanskrit, Tibetan |

## Windows 10

The list of fonts included with Windows 10 is available in the [Windows 10 font list](/typography/fonts/windows_10_font_list).

Windows 10 converges the Windows platform for use across multiple device categories. This section on Windows 10 covers all Windows 10 editions, including Desktop, Server and Mobile.

All Windows 10 editions support the same set of scripts. In addition to the scripts supported in earlier Windows releases, Windows 10 adds support for several historic scripts. These scripts are supported using the new Segoe UI Historic font.

The following table lists scripts newly supported in Windows 10, and associated fonts:

| New scripts | Region where script is from | Fonts | Comments on language usage |
| ----------- | --------------------------- | ----- | -------------------------- |
| ADLaM                     | Africa              | Ebrima            | Fulani   |
| Brahmi                    | Indian subcontinent | Segoe UI Historic | Historic |
| Carian                    | Europe              | Segoe UI Historic | Historic |
| Cypriot                   | Europe              | Segoe UI Historic | Historic |
| Egyptian Hieroglyphs      | Middle East         | Segoe UI Historic | Historic |
| Imperial Aramaic          | Middle East         | Segoe UI Historic | Historic |
| Inscriptional Pahlavi     | Middle East         | Segoe UI Historic | Historic |
| Inscriptional Parthian    | Middle East         | Segoe UI Historic | Historic |
| Kharoshthi                | Indian subcontinent | Segoe UI Historic | Historic |
| Lycian                    | Europe              | Segoe UI Historic | Historic |
| Lydian                    | Europe              | Segoe UI Historic | Historic |
| Meetei Mayek              | Indian subcontinent | Nirmala UI        | Meitei   |
| Phoenician                | Middle East         | Segoe UI Historic | Historic |
| Old Persian Cuneiform     | Middle East         | Segoe UI Historic | Historic |
| Old South Arabian         | Middle East         | Segoe UI Historic | Historic |
| Shavian                   | Europe              | Segoe UI Historic | English phonetic writing |
| Sumero-Akkadian Cuneiform | Middle East         | Segoe UI Historic | Historic |
| Ugaritic Cuneiform        | Middle East         | Segoe UI Historic | Historic |

Certain other historic scripts were supported in earlier versions in the Segoe UI Symbol font.
In order to avoid duplication, the following scripts were from Segoe UI Symbol and included in Segoe UI Historic:

- Glagolitic
- Gothic
- Meroitic Cursive
- Ogham
- Old Italic
- Orkhon
- Runic

In Windows 8.1, the Meiryo UI font family was used for Japanese text in the Windows user interface.
On Windows Phone 8.1, the popular Yu Gothic font was used for Japanese.
In Windows 10, the user interface font family for Japanese changed to Yu Gothic UI for all editions.
To make Yu Gothic UI perform as intended in Windows user interfaces, Yu Gothic UI is adapted from Yu Gothic with certain metric and character width modifications, and alternate glyphs for Latin characters.
For nonuser interface content, the Yu Gothic fonts are still included.
For optimal readability, the OpenType “palt” feature (proportional alternate widths) should be enabled for text formatted with Yu Gothic.

Another change pertaining to user interface fonts is that a semilight weight was to the Malgun Gothic family.
Otherwise, user interface fonts for other languages are the same as in Windows 8.1.

In Windows 8 and Windows 8.1, private-use-characters in the Segoe UI Symbol font were used for user interface iconography.
In Windows 10, the Segoe MDL2 Assets font was to provide newer iconography.

An important development in Windows 10 is the Universal Windows Platform (UWP): a converged app platform allowing a developer to create a single app that can run on all Windows devices.
Windows fonts are one aspect of this convergence: Windows 10 introduces a recommended UWP font set that is common across all editions that support UWP, including Desktop, Server, Mobile and Xbox.

For information regarding which fonts are included in the recommended Microsoft font set, complete details are provided in [Windows 7 Guidelines for fonts](/windows/desktop/uxguide/vis-fonts).
One important point to note is that the recommended font set doesn't include all of the weights for certain font families.
In particular, due to the large size of East Asian fonts, only the regular weight of East Asian font families are included in the recommended font set.

Many additional fonts are available for Desktop and Server, including all other fonts from previous releases.
However, not all of these fonts are preinstalled by default in all images.
In order to make disk usage and font choices more relevant to users according to the languages that they use, many fonts were moved into optional, on-demand packages.
These packages are designed around the different scripts that fonts are primarily intended to support. Windows Update installs most of these packages automatically when the associated languages are enabled in language settings (for example, by enabling a keyboard). However, you can install any of the optional font packages manually in Settings. The Pan-European Supplemental Fonts package isn't triggered automatically but can be added by enabling it in Settings.

To add font packages manually, go to Settings &gt; System &gt; Installed apps &gt; Manage optional features.

The following are the optional font packages that are automatically installed based on changes to language settings:

- Arabic Script Supplemental Fonts
- Bangla Script Supplemental Fonts
- Canadian Aboriginal Syllabics Supplemental Fonts
- Cherokee Supplemental Fonts
- Chinese (Simplified) Supplemental Fonts
- Chinese (Traditional) Supplemental Fonts
- Devanagari Supplemental Fonts
- Ethiopic Supplemental Fonts
- Gujarati Supplemental Fonts
- Gurmukhi Supplemental Fonts
- Hebrew Supplemental Fonts
- Japanese Supplemental Fonts
- Khmer Supplemental Fonts
- Kannada Supplemental Fonts
- Korean Supplemental Fonts
- Lao Supplemental Fonts
- Malayalam Supplemental Fonts
- Odia Supplemental Fonts
- Sinhala Supplemental Fonts
- Syriac Supplemental Fonts
- Tamil Supplemental Fonts
- Telugu Supplemental Fonts
- Thai Supplemental Fonts

The following optional font package must be installed manually:

- Pan-European Supplemental Fonts

Note: These optional packages are for Desktop and Server editions only.

Moving these fonts into optional packages provides over 220 MB of disk savings for users who don’t require these fonts.

Another significant international development in Windows 10 is the introduction of a new complex-script shaping engine, the Universal Shaping Engine. The Universal Shaping Engine allows any complex script in Unicode 7.0 to be shaped correctly even if the script isn't yet supported by a system-provided font.
Users can install a suitable OpenType font for correct shaping behavior for any script in Unicode 7.0.

Note: While the Windows platform is able to support display of additional Unicode 7.0 scripts using nonsystem fonts, it doesn’t guarantee that using nonsystem fonts will work in all apps.
In particular, apps that do their own low-level text-display processing might not display a script correctly unless they were explicitly designed to support that script, even if they call platform APIs that use the universal shaping engine.
Also note that platform frameworks don't provide font fallback behavior using nonsystem fonts.

The following complex scripts in Unicode 7.0 are supported in the Universal Shaping Engine.

Balinese, Batak, Brahmi, Buginese, Buhid, Chakma, Cham, Duployan, Egyptian Hieroglyphs, Grantha, Hanunoo, Javanese, Kaithi, Kayah Li, Kharoshthi, Khojki, Khudawadi, Lepcha, Limbu, Mahajani, Mandaic, Manichaean, Meitei Mayek, Modi, Mongolian, N’Ko, Pahawh Hmong, Phags-pa, Psalter Pahlavi, Rejang, Saurashtra, Sharada, Siddham, Sinhala, Sundanese, Syloti Nagri, Tagalog, Tagbanwa, Tai Le, Tai Tham, Tai Viet, Takri, Tibetan, Tifinagh, Tirhuta

Other scripts in Unicode 7.0 either are supported in other shaping engines or don't require complex script handling.

For more background on the Universal Shaping Engine, see [Creating and supporting OpenType fonts for the Universal Shaping Engine](/typography/script-development/use) .

## Windows 8.1

The list of fonts included with Windows 8.1 is available in the [Windows 8.1 font list](/typography/fonts/windows_81_font_list).

The following table lists scripts newly supported in Windows 8.1, and associated fonts:

| New scripts | Region where script is from | Fonts | Comments on language usage |
| ----------- | --------------------------- | ----- | -------------------------- |
| Buginese         | Southeast Asia      | Leelawadee UI   | Buginese |
| Coptic           | Middle East         | Segoe UI Symbol | Historic |
| Javanese         | Southeast Asia      | Javanese Text   | Javanese |
| Meroitic Cursive | Middle East         | Segoe UI Symbol | Historic |
| Ol Chiki         | Indian Subcontinent | Nirmala UI      | Santali |
| Sora Sompeng     | Indian Subcontinent | Nirmala UI      | Sora |

For the previously supported Khmer, Lao and Thai scripts, the fonts used for the Windows user interface were changed in Windows 8.1:

- Khmer: the Windows 8 user interface font was Khmer UI; Windows 8.1 uses Leelawadee UI
- Lao: the Windows 8 user interface font was Lao UI; Windows 8.1 uses Leelawadee UI
- Thai: the Windows 8 user interface font was Leelawadee; Windows 8.1 uses Leelawadee UI

Also, for several font families, new weights were added to extend the font weight options for content and app creators:

- Microsoft JhengHei UI: added Light weight
- Microsoft YaHei UI: added Light weight
- Nirmala UI: added Semilight weight
- Myanmar Text: added Bold weight
- Segoe UI: Black and Black Italic weights added (Latin, Greek and Cyrillic only)

Character coverage for previously supported Arabic and Hebrew scripts was extended in several fonts to include all characters in Unicode 6.2:

- Arabic script: Arial, Courier New, Microsoft Sans Serif, Segoe UI, Tahoma, Times New Roman
- Hebrew script: Aharoni Bold, Arial, Courier New, David, FrankRuehl, Levinim MT, Microsoft Sans Serif, Miriam, Miriam Fixed, Rod, Segoe UI, Tahoma, Times New Roman

A significant font addition is the Segoe UI Emoji font, and color font support.
Color fonts use an extension to the OpenType font specification.
Color font rendering using the Segoe UI Emoji font allows emoji symbol characters to be displayed using full-color glyphs that are also scalable because they use TrueType glyph outlines.
Color emoji display is supported in the DWrite text stack and enabled by default in the HTML and XAML application user interface frameworks used for Windows Store apps and in the Windows shell.

Another addition in Windows 8.1 is a collection of fonts with members optimized for different optical sizes: Sitka Small, Sitka Text, Sitka Subheading, Sitka Heading, Sitka Display, and Sitka Banner.
These fonts are designed to be used together in documents with elements at different sizes to provide readability and typographic consistency.
The Sitka fonts have basic Latin, Greek and Cyrillic coverage.
They're intended for use for print or on-screen content, but not for user interface.

## Windows 8

The list of fonts included with Windows 8 is available in the [Windows 8 font list](/typography/fonts/windows_8_font_list).

The following table lists scripts newly supported in Windows 8, and associated fonts:

| New scripts | Region where script is from | Fonts | Comments on language usage |
| ----------- | --------------------------- | ----- | -------------------------- |
| Glagolitic | Europe                | Segoe UI Symbol | Historic |
| Gothic     | Europe                | Segoe UI Symbol | Historic |
| Old Hangul | East Asia             | Malgun Gothic   | Historic, used in historic Korean texts |
| Old Italic | Europe                | Segoe UI Symbol | Historic |
| Lisu       | China, Southeast Asia | Segoe UI        | Lisu |
| Myanmar    | Southeast Asia        | Myanmar Text    | Myanmar, Shan, Karen |
| N’Ko       | Africa                | Ebrima          | N’Ko and other Manding languages |
| Orkhon     | China                 | Segoe UI Symbol | Historic |

Some significant changes were introduced into Unicode version 5.2 in relation to the encoding of Old Hangul text.
These changes enable products that can support Korean Standard KS X 1026-1:2007.
In earlier versions of Windows, Uniscribe included support for shaping Old Hangul text, though not in accordance with the KS X 1026-1:2007 standard.
In Windows 8, Uniscribe and DirectWrite provide support for Old Hangul text in accordance with the Korean standard, and font support for Old Hangul text is also now included.

In Windows 7, [Unicode variation sequences](http://www.unicode.org/faq/vs.html "Unicode variation sequences") were supported for certain scenarios only.
In Windows 8, Unicode variation sequences are fully supported in GDI and DirectWrite text stacks.
In particular, ideographic variation sequences used in Japan are supported, and the Japanese fonts in Windows 8 support several ideographic variation sequences.

For certain previously supported scripts, the fonts used for the Windows user interface were changed in Windows 8.
In some cases, support for a script was added to an existing font (such as Segoe UI); in other cases, entirely new user interface fonts for those scripts were added.
The user interface font changes are as follows:

- Ebrima font: updated to add support for Ethiopic and NʼKo scripts
- Gadugi font: new font for Canadian Aboriginal Syllabics and Cherokee scripts
- Microsoft JhengHei UI: new font for Traditional Chinese script
- Microsoft YaHei UI: new font for Simplified Chinese script
- Nirmala UI: new font for South Asian scripts (Bangla, Devanagari, Gujarati, Gurmukhi, Kannada, Malayalam, Odia, Sinhala, Tamil, Telugu)
- Segoe UI (certain weights): updated to add support for Arabic, Armenian, Georgian (Mkhedruli), Georgian Khutsuri, Hebrew scripts

Among additional fonts added for previously supported scripts is the Urdu Typesetting font, which supports Arabic script in Nastaliq style (sometimes referred to as *Perso-Arabic script*).

In Windows 7, the Segoe UI Symbol font was added to provide support for many symbols encoded in Unicode.
This font was significantly updated in Windows 8 to support many more symbols, including complete support for Emoji characters used in Japan and elsewhere.

Among other significant updates to fonts from Windows 7 is the addition of support for CJK Extension C and Extension D characters in the SimSun-ExtB and MingLiU-ExtB fonts.

In Windows 7, both Uniscribe and DirectWrite provided support for OpenType advanced typographic capabilities, including OpenType features, such as typographic small caps or stylistic sets, and language specific forms.
This functionality wasn't supported in Windows user interface frameworks, however.
As a result, advanced typographic capabilities were never visible in the Windows shell and weren't well supported in applications.
These capabilities are better supported in Windows 8, enabling higher quality typography in the Windows Store apps developed for Windows 8.
The CSS3 -ms-font-feature-settings property exposes OpenType capabilities and is supported in the MSHTML rendering engine used by IE10 and Windows Store apps built using HTML and JavaScript.
For XAML, advanced OpenType capabilities that were supported in WPF and Silverlight are also supported in the Windows Runtime XAML framework.

## Windows 7

The list of fonts included with Windows 7 is available in the [Windows 7 font list](/typography/fonts/windows_7_font_list).

The following table lists scripts newly supported in Windows 7, and associated fonts:

| New scripts | Region where script is from | Fonts | Comments on language usage |
| ----------- | --------------------------- | ----- | -------------------------- |
| Braille     | -             | Segoe user interface Symbol       | - |
| Deseret     | North America | Segoe UI Symbol       | - |
| New Tai Lue | China         | Microsoft New Tai Lue | Used for the Xishuangbanna Dai language |
| Ogham       | Europe        | Segoe UI Symbol       | Historic, used for English and Irish |
| Osmanya     | Africa        | Ebrima                | Historic script from East Africa (Somalia) |
| Phags-pa    | North Asia    | Microsoft PhagsPa     | Historic, used for several languages including Mongolian, Chinese, Tibetan and Sanskrit |
| Runic       | Europe        | Segoe UI Symbol       | - |
| Symbols     | -             | Segoe UI Symbol       | - |
| Tai Le      | China         | Microsoft Tai Le      | Used for the Dehong Dai language |
| Tifinagh    | Africa        | Ebrima                | Used for Tamazight and other Amazigh languages |
| Vai         | Africa        | Ebrima                | - |

Note: The Segoe UI Symbol font contains a subset of Unicode-encoded symbols. It isn't a symbol charset-encoded font.

In Windows 7, some true bold fonts were added to support better user interface display for Bangla, Devanagari, Gujarati, Gurmukhi, Kannada, Khmer, Lao, Malayalam, Odia, Sinhala, Tamil and Telugu script.
Some fonts for already-supported scripts were updated to include support for Unicode 5.1.

Windows 7 added support for Unicode variation-selector sequences for Phags-pa script and math symbols.
 This support makes use of OpenType format 14 cmap subtables in Microsoft PhagsPa and Cambria Math fonts.

As part of on-going work to provide next-generation graphics, Windows 7 introduced a new text stack, DirectWrite.
The OpenType and complex-script functionality that has been part of Uniscribe was fully integrated into the DirectWrite text stack with the result that the DirectWrite and GDI text stacks have complete parity in script and language support.

## Windows Vista

The following table lists scripts newly supported in Windows Vista, and associated fonts:

| New scripts | Region where script is from | Fonts | Comments on language usage |
| ----------- | --------------------------- | ----- | -------------------------- |
| Canadian Syllabics | North America       | Euphemia           | Used for several languages, including Inuktitut and Cree |
| Cherokee           | North America       | Plantagenet        | - |
| Ethiopic           | Africa              | Nyala              | Used for Amharic, Tigrinya, and other languages |
| Khmer              | Southeast Asia      | DaunPenh MoolBoran | - |
| Lao                | Southeast Asia      | DokChampa          | - |
| Mongolian          | North Asia          | Mongolian Baiti    | - |
| Odia               | Indian subcontinent | Kalinga            | - |
| Sinhala            | Indian subcontinent | Iskoola Pota       | - |
| Tibetan            | Central Asia        | Microsoft Himalaya | - |
| Yi                 | China               | Microsoft Yi Baiti | - |

In Windows Vista and later versions, text-display support for all scripts and languages is always enabled in all editions.

Character coverage for several already-supported scripts was extended to Unicode 4.1 or 5.0.
Several fonts were updated accordingly.
In particular, support for Latin, Greek, Cyrillic, Hebrew and Arabic was extended in the “core” fonts:

- Arial
- Courier New
- Microsoft Sans Serif
- Tahoma
- Times New Roman

The new Aero-theme user interface font, Segoe UI, also provides Unicode 5.0 support for Latin, Greek, Cyrillic and Arabic.
Unicode 5.0 additions were also made to other Arabic fonts and several of the Indic-script fonts.

Extension B fonts for the SimSun and MingLiU families were added, as well as a variation of MingLiU with HKSCS support.

The Uighur language uses Arabic script, which was already supported.
However, a different font is required for Uighur typography.
The Microsoft Uighur font was added to support Uighur typography.

Uniscribe’s font fallback mechanism for Unicode supplementary planes was enhanced to support different fallback fonts depending on the starting font.
In this way, fallback for CJK Extension B characters uses appropriate fonts for the given language.
For example, for user interface displayed using the SimSun font (Simplified Chinese), the fallback font for Extension B is SimSun-ExtB.

New APIs were added to Uniscribe to support OpenType advanced typographic functionality in non-complex scripts.
This provides a way for clients to expose advanced font capabilities such as language-specific glyphs; discretionary ligatures; true typographic small caps, superscripts and subscripts; old-style and tabular digits.

Windows Vista includes the Cambria Math font, which has additional tables used to support layout of mathematical formulas.
Note that special software support is also required to render math formulas.
Mathematical formula support is provided in Microsoft Office 2007, but not in Windows Vista text-stack components.

Prior to Windows Vista, Uniscribe had Arabic, Hebrew and Thai shaping engines that worked with legacy, pre-OpenType fonts, but not for fonts that support those scripts using OpenType glyph substitution and positioning mechanisms.
The versions of fonts for Arabic, Hebrew and Thai included in Windows Vista were changed to use OpenType.
This means that those fonts won't work with earlier versions of Uniscribe.

## Windows XP SP2

The following table lists scripts newly supported in Windows XP SP2, and associated fonts:

| New scripts | Region where script is from | Fonts | Comments on language usage |
| ----------- | --------------------------- | ----- | -------------------------- |
| Bangla    | Indian subcontinent | Vrinda  | Used for the Assamese language and Bangla |
| Malayalam | Indian subcontinent | Kartika | - |

As with Windows XP (RTM), the **Regional and Language Options** control panel (intl.cpl) has two option controls to enable “complex script and right-to-left languages” (Arabic, Hebrew, Thaana, Indic scripts and Thai) and CJK (Chinese, Japanese, Korean). One effect of these options is to enable the Uniscribe component within the text stack.
Whereas in the RTM version, Uniscribe isn't enabled by default in all SKUs, in SP2 it's always enabled by default.

## Windows XP

The following table lists scripts newly supported in Windows XP, and associated fonts:

| New scripts | Region where script is from | Fonts | Comments on language usage |
| ----------- | --------------------------- | ----- | -------------------------- |
| Gujarati | Indian subcontinent | Shruti            | - |
| Gurmukhi | Indian subcontinent | Raavi             | Used in India for the Punjabi language |
| Kannada  | Indian subcontinent | Tunga             | - |
| Syriac   | Middle East         | Estrangelo Edessa | - |
| Telugu   | Indian subcontinent | Gautami           | - |
| Thaana   | Indian subcontinent | MV Boli           | Used for the Divehi language |

The font fallback mechanism in Uniscribe was extended to support fallback for Unicode supplementary planes: for each plane from 1 to 16, a single fallback font can be specified in the registry.

This change, along with earlier changes in Windows 2000, to support supplementary-plane characters allows Windows XP to support CJK Extension B characters.

Note: all of the scripts mentioned are supported on Windows XP, but enablement isn't activated for all of them on all language versions of Windows XP.
The **Regional and Language Options** control panel (intl.cpl) has two option controls: one to enable “complex script and right-to-left languages” (Arabic, Hebrew, Thaana, Indic scripts and Thai), and one to enable CJK (Chinese, Japanese, and Korean).
Each of these might be enabled or disabled by default, depending on the language version.
CJK fonts aren't installed by default on non-CJK versions but are included in the distribution media and will be installed when CJK support is enabled.

## Windows 2000

Windows 2000 was the first version of the Windows operating system that included the Uniscribe component, usp10.dll.
The lpk.dll library, which provides the interfaces between Uniscribe and various GDI and User APIs, was also added.
Functional benefits of Uniscribe included:

- Shaping support for complex scripts such as Arabic and Thai were brought together in a single library, allowing all language versions of Windows 2000 to be built from a single source and to display text in any supported script.
  Previously, text-display support for particular languages was added to localized versions.

- Some new complex scripts were supported.

- Font fallback for different scripts was provided.
  This is done in Uniscribe ScriptString\* APIs that are typically used in user interface components.

Support for basic Latin, Greek, Cyrillic and CJK existed with APIs in Windows NT 4.0 and Windows ME.
“Basic” here means no combining marks, and Unicode Basic Multilingual Plane only.
In relation to complex scripts, support for Arabic, Hebrew and Thai existed in previous versions and was consolidated in Windows 2000 in the Uniscribe component.
Various GDI mechanisms that might have originated in East Asian versions (font association, EUDC font support, and “JPN98FixPitch” display mode) were all present in the consolidated code base for Windows 2000.

The following table lists scripts newly supported in Windows 2000, and associated fonts:

| New scripts | Region where script is from | Fonts | Comments on language usage |
| ----------- | --------------------------- | ----- | -------------------------- |
| Armenian   | Eurasia             | Sylfaen | - |
| Devanagari | Indian subcontinent | Mangal  | Used for many languages including Hindi, Marathi, Sanskrit |
| Georgian   | Eurasia             | Sylfaen | - |
| Tamil      | Indian subcontinent | Latha   | - |

In a default setup, not all scripts are necessarily enabled.
In the **Regional Options** control panel (intl.cpl), the **General** tab includes a list of 16 language/script categories (“language groups”) that can be individually enabled or disabled.
The language group for the UI language can't be disabled, however.
When a language group is enabled, various support files are copied from the CD, including fonts. In the case of “complex-script” language groups (Arabic, Hebrew, Indic, Thai, and Vietnamese), registry entries to activate Uniscribe are also added.

The 16 language groups available on Windows 2000 are: Arabic, Armenian, Baltic, Central European, Cyrillic, Georgian, Greek, Hebrew, Indic, Japanese, Korean, Simplified Chinese, Thai, Traditional Chinese, Turkic, Vietnamese, Western Europe and United States.

A *surrogates* shaping engine was also added to Uniscribe to allow display of Unicode supplementary-plane characters in the GDI text stack.
GDI supports wide characters but doesn't understand UTF-16 surrogate pairs.
See [Surrogate Pairs](../encoding/unicode-standard.md#surrogate-pairs) and [Variation Selection](../encoding/unicode-standard.md#variation-selection) for details on the extent of support for supplementary-plan characters.
Windows 2000 didn't include fonts for any supplementary-plane characters.
