

# Script and Font Support in Windows

Since before Windows 2000, text-display support for new scripts has been added in each major release of Windows. This article describes changes made in each major release.

Note that support for a script may require certain changes to text stack components as well as changes to fonts. The Windows operating system has many text stack components: DirectWrite, GDI, Uniscribe, GDI+, WPF, RichEdit, ComCtl32, and others. The information provided here pertains primarily to GDI and DirectWrite. It is also generally applicable to UI frameworks such as RichEdit or the MSHTML rendering agent used for Windows apps and for rendering Web content, though those components may exhibit certain differences.

Comments on language usage are included in cases in which associations between scripts and languages may not be well known. The list of languages for any given script is not necessarily exhaustive.

## On This Page

-   [Windows 10](#_Windows_10)
-   [Windows 8.1](#_Windows_8.1)
-   [Windows 8](#_Windows_8)
-   [Windows 7](#_Windows_7)
-   [Windows Vista](#_Windows_Vista)
-   [Windows XP SP2](#_Windows_XP_SP2)
-   [Windows XP](#_Windows_XP)
-   [Windows 2000](#_Windows_2000)

## Windows 10

Windows 10 converges the Windows platform for use across multiple device categories. The description above of previous releases applies to Windows Client (desktop) and Server editions. This section on Windows 10 covers all Windows 10 editions, including Desktop, Server and Mobile.

All Windows 10 editions support the same set of scripts. In addition to the scripts supported in earlier Windows releases, Windows 10 adds support for several additional, historic scripts. These are supported using the new Segoe UI Historic font:

**New scripts**

**Region where script is from**

**Fonts**

**Comments on language usage**

Brahmi

Indian subcontinent

Segoe UI Historic

Historic

Carian

Europe

Segoe UI Historic

Historic

Cypriot

Europe

Segoe UI Historic

Historic

Egyptian Hieroglyphs

Middle East

Segoe UI Historic

Historic

Imperial Aramaic

Middle East

Segoe UI Historic

Historic

Inscriptional Pahlavi

Middle East

Segoe UI Historic

Historic

Inscriptional Parthian

Middle East

Segoe UI Historic

Historic

Kharoshthi

Indian subcontinent

Segoe UI Historic

Historic

Lycian

Europe

Segoe UI Historic

Historic

Lydian

Europe

Segoe UI Historic

Historic

Phoenician

Middle East

Segoe UI Historic

Historic

Old Persian Cuneiform

Middle East

Segoe UI Historic

Historic

Old South Arabian

Middle East

Segoe UI Historic

Historic

Shavian

Europe

Segoe UI Historic

English phonetic writing

Sumero-Akkadian Cuneiform

Middle East

Segoe UI Historic

Historic

Ugaritic Cuneiform

Middle East

Segoe UI Historic

Historic

Certain other historic scripts were supported in earlier versions in the Segoe UI Symbol font. In order to avoid duplication, the following scripts have been removed from Segoe UI Symbol and included in Segoe UI Historic:

-   Glagolitic
-   Gothic
-   Meroitic Cursive
-   Ogham
-   Old Italic
-   Orkhon
-   Runic

In Windows 8.1, the Meiryo UI font family was used for Japanese text in the Windows user interface. On Windows Phone 8.1, the popular Yu Gothic font was used for Japanese. In Windows 10, the user interface font family for Japanese has changed to Yu Gothic UI for all editions. In order to make Yu Gothic UI perform as intended in Windows UI, Yu Gothic UI is adapted from Yu Gothic with certain metric and character width modifications as well as alternate glyphs for Latin characters. For non-UI content, the Yu Gothic fonts are still included. For optimal readability, the OpenType “palt” feature (proportional alternate widths) should be enabled for text formatted with Yu Gothic.

Another change pertaining to user interface fonts is that a semilight weight has been added to the Malgun Gothic family. Otherwise, user interface fonts for other languages are the same as in Windows 8.1.

In Windows 8 and Windows 8.1, private-use-characters in the Segoe UI Symbol font were used for user interface iconography. In Windows 10, the Segoe MDL2 Assets font has been added to provide newer iconography.

An important development in Windows 10 is the Universal Windows Platform (UWP): a converged app platform allowing a developer to create a single app that can run on all Windows devices. Windows fonts are one aspect of this convergence: Windows 10 introduces a recommended UWP font set that is common across all editions that support UWP, including Desktop, Server, Mobile and Xbox.

For information regarding which fonts are included in the recommended UWP font set, complete details are provided in [Guidelines for fonts](http://go.microsoft.com/fwlink/p/?LinkId=534935). One important point to note is that the recommended font set does not include all of the weights for certain font families. In particular, due to the large size of East Asian fonts, only the regular weight of East Asian font families are included in the recommended font set.

A number of additional fonts are available for Desktop and Server, including all other fonts from previous releases. However, not all of these are pre-installed by default in all images. In order to make disk usage and font choices more relevant to users according to the languages that they use, a number of fonts have been moved into optional, on-demand packages. These packages are designed around the different scripts that fonts are primarily intended to support, and most are installed automatically by Windows Update when the associated languages are enabled in language settings (for example, by enabling a keyboard).

Any of these optional font packages can also be installed manually by any user in Settings. One package is not triggered automatically but can be added by enabling it in Settings. To add font packages manually, go to Settings &gt; System &gt; Installed apps &gt; Manage optional features.

The following are the optional font packages that are automatically installed based on changes to language settings:

-   Arabic Script Supplemental Fonts
-   Bangla Script Supplemental Fonts
-   Canadian Aboriginal Syllabics Supplemental Fonts
-   Cherokee Supplemental Fonts
-   Chinese (Simplified) Supplemental Fonts
-   Chinese (Traditional) Supplemental Fonts
-   Devanagari Supplemental Fonts
-   Ethiopic Supplemental Fonts
-   Gujarati Supplemental Fonts
-   Gurmukhi Supplemental Fonts
-   Hebrew Supplemental Fonts
-   Japanese Supplemental Fonts
-   Khmer Supplemental Fonts
-   Kannada Supplemental Fonts
-   Korean Supplemental Fonts
-   Lao Supplemental Fonts
-   Malayalam Supplemental Fonts
-   Odia Supplemental Fonts
-   Sinhala Supplemental Fonts
-   Syriac Supplemental Fonts
-   Tamil Supplemental Fonts
-   Telugu Supplemental Fonts
-   Thai Supplemental Fonts

The following optional font package must be installed manually:

-   Pan-European Supplemental Fonts

Note: These optional packages are for Desktop and Server editions only.

Moving these fonts into optional packages provides over 220 MB of disk savings for users who don’t require these fonts.

Another significant international development in Windows 10 is the introduction of a new complex-script shaping engine — the Universal Shaping Engine — that allows any complex script in Unicode 7.0 to be shaped correctly even if the script is not yet supported by a system-provided font. Users have the option to install a suitable OpenType font for correct shaping behavior for any script in Unicode 7.0.

Note: While the Windows platform is able to support display of additional Unicode 7.0 scripts using non-system fonts, this doesn’t not guarantee that this will work in all apps. In particular, apps that do their own low-level text-display processing may not display a script correctly unless they were explicitly designed to support that script, even if they call platform APIs that use the universal shaping engine. Also note that platform frameworks will not provide font fallback behavior using non-system fonts.

The following complex scripts in Unicode 7.0 are supported in the Universal Shaping Engine.

Balinese, Batak, Brahmi, Buginese, Buhid, Chakma, Cham, Duployan, Egyptian Hieroglyphs, Grantha, Hanunoo, Javanese, Kaithi, Kayah Li, Kharoshthi, Khojki, Khudawadi, Lepcha, Limbu, Mahajani, Mandaic, Manichaean, Meitei Mayek, Modi, Mongolian, N’Ko, Pahawh Hmong, Phags-pa, Psalter Pahlavi, Rejang, Saurashtra, Sharada, Siddham, Sinhala, Sundanese, Syloti Nagri, Tagalog, Tagbanwa, Tai Le, Tai Tham, Tai Viet, Takri, Tibetan, Tifinagh, Tirhuta

Other scripts in Unicode 7.0 either are supported in other shaping engines or do not require complex script handling.

For more background on the Universal Shaping Engine, see [Windows shapes the world’s languages](http://blogs.windows.com/bloggingwindows/2015/02/23/windows-shapes-the-worlds-languages/) .

[Top of page](#content)

## Windows 8.1

The following table lists scripts newly supported in Windows 8.1, and associated fonts:

**New scripts**

**Region where script is from**

**Fonts**

**Comments on language usage**

Buginese

Southeast Asia

Leelawadee UI

Buginese

Coptic

Middle East

Segoe UI Symbol

Historic

Javanese

Southeast Asia

Javanese Text

Javanese

Meroitic Cursive

Middle East

Segoe UI Symbol

Historic

Ol Chiki

Indian Subcontinent

Nirmala UI

Santali

Sora Sompeng

Indian Subcontinent

Nirmala UI

Sora

For the previously-supported Khmer, Lao and Thai scripts, the fonts used for the Windows user interface were changed in Windows 8.1:

-   Khmer: the Windows 8 UI font was Khmer UI; Windows 8.1 uses Leelawadee UI
-   Lao: the Windows 8 UI font was Lao UI; Windows 8.1 uses Leelawadee UI
-   Thai: the Windows 8 UI font was Leelawadee; Windows 8.1 uses Leelawadee UI

Also, for several font families, new weights were added to extend the font weight options for content and app creators:

-   Microsoft JhengHei UI: added Light weight
-   Microsoft YaHei UI: added Light weight
-   Nirmala UI: added Semilight weight
-   Myanmar Text: added Bold weight
-   Segoe UI: Black and Black Italic weights added (Latin, Greek and Cyrillic only)

Character coverage for previously-supported Arabic and Hebrew scripts was extended in several fonts to include all characters in Unicode 6.2:

-   Arabic script: Arial, Courier New, Microsoft Sans Serif, Segoe UI, Tahoma, Times New Roman
-   Hebrew script: Aharoni Bold, Arial, Courier New, David, FrankRuehl, Levinim MT, Microsoft Sans Serif, Miriam, Miriam Fixed, Rod, Segoe UI, Tahoma, Times New Roman

A significant font addition is the Segoe UI Emoji font, and color font support. Color fonts use an extension to the OpenType font specification. Color font rendering using the Segoe UI Emoji font allows emoji symbol characters to be displayed using full-color glyphs that are also scalable because they use TrueType glyph outlines. Color emoji display is supported in the DWrite text stack and enabled by default in the HTML and XAML application UI frameworks used for Windows Store apps and in the Windows shell.

Another addition in Windows 8.1 is a collection of fonts with members optimized for different optical sizes: Sitka Small, Sitka Text, Sitka Subheading, Sitka Heading, Sitka Display, and Sitka Banner. These fonts are designed to be used together in documents with elements at different sizes to provide readability and typographic consistency. The Sitka fonts have basic Latin, Greek and Cyrillic coverage. They are intended for use for print or on-screen content, but not for UI.

[Top of page](#content)

## Windows 8

The following table lists scripts newly supported in Windows 8, and associated fonts:

**New scripts**

**Region where script is from**

**Fonts**

**Comments on language usage**

Glagolitic

Europe

Segoe UI Symbol

Historic

Gothic

Europe

Segoe UI Symbol

Historic

Old Hangul

East Asia

Malgun Gothic

Historic, used in historic Korean texts

Old Italic

Europe

Segoe UI Symbol

Historic

Lisu

China, Southeast Asia

Segoe UI

Lisu

Myanmar

Southeast Asia

Myanmar Text

Myanmar, Shan, Karen

N’Ko

Africa

Ebrima

N’Ko and other Manding languages

Orkhon

China

Segoe UI Symbol

Historic

Some significant changes were introduced into Unicode version 5.2 in relation to the encoding of Old Hangul text. These changes enable products that can support Korean Standard KS X 1026-1:2007. In earlier versions of Windows, Uniscribe included support for shaping Old Hangul text, though not in accordance with the KS X 1026-1:2007 standard. In Windows 8, Uniscribe and DirectWrite provide support for Old Hangul text in accordance with the Korean standard, and font support for Old Hangul text is also now included.

In Windows 7, [Unicode variation sequences](http://www.unicode.org/faq/vs.html "Unicode variation sequences") were supported for certain scenarios only. In Windows 8, Unicode variation sequences are fully supported in GDI and DirectWrite text stacks. In particular, ideographic variation sequences used in Japan are supported, and the Japanese fonts in Windows 8 support a number of ideographic variation sequences.

For certain previously-supported scripts, the fonts used for the Windows user interface were changed in Windows 8. In some cases, support for a script was added to an existing font (such as Segoe UI); in other cases, entirely new UI fonts for those scripts were added. The UI font changes are as follows:

-   Ebrima font: updated to add support for Ethiopic and NʼKo scripts
-   Gadugi font: new font for Canadian Aboriginal Syllabics and Cherokee scripts
-   Microsoft JhengHei UI: new font for Traditional Chinese script
-   Microsoft YaHei UI: new font for Simplified Chinese script
-   Nirmala UI: new font for South Asian scripts (Bangla, Devanagari, Gujarati, Malayalam, Odia, Telugu)
-   Segoe UI (certain weights): updated to add support for Arabic, Armenian, Georgian (Mkhedruli), Georgian Khutsuri, Hebrew scripts

Among additional fonts added for previously-supported scripts is the Urdu Typesetting font, which supports Arabic script in Nastaliq style (sometimes referred to as   *Perso-Arabic script* ).

In Windows 7, the Segoe UI Symbol font was added to provide support for many symbols encoded in Unicode. This font has been significantly updated in Windows 8 to support many more symbols, including complete support for Emoji characters used in Japan and elsewhere.

Among other significant updates to fonts from Windows 7 is the addition of support for CJK Extension C and Extension D characters in the SimSun-ExtB and MingLiU-ExtB fonts.

In Windows 7, both Uniscribe and DirectWrite provided support for OpenType advanced typographic capabilities, including OpenType features, such as typographic small caps or stylistic sets, and language specific forms. This functionality was not supported in Windows UI frameworks, however. As a result, advanced typographic capabilities were never visible in the Windows shell and were not well supported in applications. These capabilities are better supported in Windows 8, enabling higher quality typography in the Windows Store apps developed for Windows 8. The CSS3 -ms-font-feature-settings property exposes OpenType capabilities and is supported in the MSHTML rendering engine used by IE10 and Windows Store apps built using HTML and JavaScript. For XAML, advanced OpenType capabilities that were supported in WPF and Silverlight are also supported in the Windows Runtime XAML framework.

[Top of page](#content)

## Windows 7

The following table lists scripts newly supported in Windows 7, and associated fonts:

**New scripts**

**Region where script is from**

**Fonts**

**Comments on language usage**

Braille

 

Segoe UI Symbol

 

Deseret

North America

Segoe UI Symbol

 

New Tai Lue

China

Microsoft New Tai Lue

Used for the Xishuangbanna Dai language

Ogham

Europe

Segoe UI Symbol

Historic, used for English and Irish

Osmanya

Africa

Ebrima

Historic script from East Africa (Somalia)

Phags-pa

North Asia

Microsoft PhagsPa

Historic, used for several languages including Mongolian, Chinese, Tibetan and Sanskrit

Runic

Europe

Segoe UI Symbol

 

Symbols

 

Segoe UI Symbol

 

Tai Le

China

Microsoft Tai Le

Used for the Dehong Dai language

Tifinagh

Africa

Ebrima

Used for Tamazight and other Amazigh languages

Vai

Africa

Ebrima

 

Note: The Segoe UI Symbol font contains a subset of Unicode-encoded symbols. It is not a symbol charset-encoded font.

In Windows 7, some true bold fonts were added to support better UI display for Bengali, Devanagari, Gujarati, Gurmukhi, Kannada, Khmer, Lao, Malayalam, Oriya, Sinhala, Tamil and Telugu script. Some fonts for already-supported scripts were updated to include support for Unicode 5.1.

Windows 7 added support for Unicode variation-selector sequences for Phags-pa script and math symbols. This support makes use of OpenType format 14 cmap subtables in Microsoft PhagsPa and Cambria Math fonts.

As part of on-going work to provide next-generation graphics, Windows 7 introduced a new text stack, DirectWrite. The OpenType and complex-script functionality that has been part of Uniscribe was fully integrated into the DirectWrite text stack with the result that the DirectWrite and GDI text stacks have complete parity in script and language support.

## Windows Vista

The following table lists scripts newly supported in Windows Vista, and associated fonts:

**New scripts**

**Region where script is from**

**Fonts**

**Comments on language usage**

Canadian Syllabics

North America

Euphemia

Used for several languages, including Inuktitut and Cree

Cherokee

North America

Plantagenet

 

Ethiopic

Africa

Nyala

Used for Amharic, Tigrinya, and other languages

Khmer

Southeast Asia

DaunPenh MoolBoran

 

Lao

Southeast Asia

DokChampa

 

Mongolian

North Asia

Mongolian Baiti

 

Odia

Indian subcontinent

Kalinga

 

Sinhala

Indian subcontinent

Iskoola Pota

 

Tibetan

Central Asia

Microsoft Himalaya

 

Yi

China

Microsoft Yi Baiti

 

In Windows Vista and later versions, text-display support for all scripts and languages is always enabled in all editions.

Character coverage for several already-supported scripts was extended to Unicode 4.1 or 5.0. Several fonts were updated accordingly. In particular, support for Latin, Greek, Cyrillic, Hebrew and Arabic was extended in the “core” fonts:

-   Arial
-   Courier New
-   Microsoft Sans Serif
-   Tahoma
-   Times New Roman

(The new Aero-theme UI font, Segoe UI, also provides Unicode 5.0 support for Latin, Greek, Cyrillic and Arabic.) Unicode 5.0 additions were also made to other Arabic fonts as well as several of the Indic-script fonts.

Extension B fonts for the SimSun and MingLiU families were added, as well as a variation of MingLiU with HKSCS support.

The Uighur language uses Arabic script, which was already supported. However, a different font is required for Uighur typography. The Microsoft Uighur font was added to support this.

Uniscribe’s font fallback mechanism for Unicode supplementary planes was enhanced to support different fallback fonts depending on the starting font. In this way, fallback for CJK Extension B characters uses appropriate fonts for the given language. For example, for UI displayed using the SimSun font (Simplified Chinese), the fallback font for Extension B is SimSun-ExtB.

New APIs were added to Uniscribe to support OpenType advanced typographic functionality in non-complex scripts. This provides a way for clients to expose advanced font capabilities such as language-specific glyphs; discretionary ligatures; true typographic small caps, superscripts and subscripts; old-style as well as tabular digits.

Windows Vista includes the Cambria Math font, which has additional tables used to support layout of mathematical formulas. Special software support is also required to render math formulas, however. This is provided in Microsoft Office 2007, but not in Windows Vista text-stack components.

Prior to Windows Vista, Uniscribe had Arabic, Hebrew and Thai shaping engines that worked with legacy, pre-OpenType fonts, but not for fonts that support those scripts using OpenType glyph substitution and positioning mechanisms. The versions of fonts for Arabic, Hebrew and Thai that shipped in Windows Vista were changed to use OpenType. This means that those fonts will not work with earlier versions of Uniscribe.

[Top of page](#content)

## Windows XP SP2

The following table lists scripts newly supported in Windows XP SP2, and associated fonts:

**New scripts**

**Region where script is from**

**Fonts**

**Comments on language usage**

Bangla

Indian subcontinent

Vrinda

Used for the Assamese language as well as Bangla

Malayalam

Indian subcontinent

Kartika

 

As with Windows XP (RTM), the **Regional and Language Options** control panel (intl.cpl) has two option controls to enable “complex script and right-to-left languages” (Arabic, Hebrew, Thaana, Indic scripts and Thai) and CJK (Chinese, Japanese, Korean). One effect of these options is to enable the Uniscribe component within the text stack. Whereas in the RTM version, Uniscribe is not enabled by default in all SKUs, in SP2 it is always enabled by default.

[Top of page](#content)

## Windows XP

The following table lists scripts newly supported in Windows XP, and associated fonts:

**New scripts**

**Region where script is from**

**Fonts**

**Comments on language usage**

Gujarati

Indian subcontinent

Shruti

 

Gurmukhi

Indian subcontinent

Raavi

Used in India for the Punjabi language

Kannada

Indian subcontinent

Tunga

 

Syriac

Middle East

Estrangelo Edessa

 

Telugu

Indian subcontinent

Gautami

 

Thaana

Indian subcontinent

MV Boli

Used for the Divehi language

The font fallback mechanism in Uniscribe was extended to support fallback for Unicode supplementary planes: for each plane from 1 to 16, a single fallback font can be specified in the registry.

This change, along with earlier changes in Windows 2000, to support supplementary-plane characters allows Windows XP to support CJK Extension B characters.

Note: all of the scripts mentioned are supported on Windows XP, but enablement is not activated for all of them on all language versions of Windows XP. The **Regional and Language Options** control panel (intl.cpl) has two option controls: one to enable “complex script and right-to-left languages” (Arabic, Hebrew, Thaana, Indic scripts and Thai), and one to enable CJK (Chinese, Japanese, and Korean). Each of these may be enabled or disabled by default, depending on the language version. CJK fonts are not installed by default on non-CJK versions but are included in the distribution media and will be installed when CJK support is enabled.

[Top of page](#content)

## Windows 2000

Windows 2000 was the first version of the Windows operating system that included the Uniscribe component, usp10.dll. (The lpk.dll library, which provides the interfaces between Uniscribe and various GDI and User APIs, was also added.) Functional benefits of Uniscribe included:

-   Shaping support for complex scripts such as Arabic and Thai were brought together in a single library, allowing all language versions of Windows 2000 to be built from a single source and to display text in any supported script. (Previously, text-display support for particular languages was added to localized versions.)
-   Some new complex scripts were supported.
-   Font fallback for different scripts was provided. (This is done in Uniscribe ScriptString\* APIs that are typically used in UI components.)

Support for basic Latin, Greek, Cyrillic and CJK existed with APIs in Windows NT 4.0 and Windows ME. (“Basic” here means no combining marks, and Unicode Basic Multilingual Plane only.) In relation to complex scripts, support for Arabic, Hebrew and Thai existed in previous versions and was consolidated in Windows 2000 in the Uniscribe component. Various GDI mechanisms that may have originated in East Asian versions (font association, EUDC font support, and “JPN98FixPitch” display mode) were all present in the consolidated code base for Windows 2000.

The following table lists scripts newly supported in Windows 2000, and associated fonts:

**New scripts**

**Region where script is from**

**Fonts**

**Comments on language usage**

Armenian

Eurasia

Sylfaen

 

Devanagari

Indian subcontinent

Mangal

Used for many languages including Hindi, Marathi, Sanskrit

Georgian

Eurasia

Sylfaen

 

Tamil

Indian subcontinent

Latha

 

In a default setup, not all scripts are necessarily enabled. In the **Regional Options** control panel (intl.cpl), the **General** tab includes a list of sixteen language/script categories (“language groups”) that can be individually enabled or disabled. (The language group for the UI language cannot be disabled, however.) When a language group is enabled, various support files are copied from the CD, including fonts; in the case of “complex-script” language groups (Arabic, Hebrew, Indic, Thai, and Vietnamese), registry entries to activate Uniscribe are also added.

The sixteen language groups available on Windows 2000 are: Arabic, Armenian, Baltic, Central European, Cyrillic, Georgian, Greek, Hebrew, Indic, Japanese, Korean, Simplified Chinese, Thai, Traditional Chinese, Turkic, Vietnamese, Western Europe and United States.

A *surrogates* shaping engine was also added to Uniscribe to allow display of Unicode supplementary-plane characters in the GDI text stack. (GDI supports wide characters but does not understand UTF-16 surrogate pairs.) See the [Surrogates and Supplementary Characters](https://msdn.microsoft.com/globalization/mt683846) topic for details on the extent of support for supplementary-plan characters. Windows 2000 did not include fonts for any supplementary-plane characters.

[Top of page](#content)


