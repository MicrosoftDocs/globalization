---
title: Other locale representations
description: There are a number of other locale identification systems that you should be aware of, such as LCID (obsolete Windows Locale Identifier).
author: m-kauppinen
ms.author: v-mikau
ms.topic: conceptual #Required; leave this attribute/value as-is.
ms.date: 03/13/2023

---
# Other locale representations

Many environments, such as C++, Java, .NET Framework, Python, XML, and other Unicode-based environments use a common format for specifying a locale. This format is specified in the [IETF BCP 47](https://www.ietf.org/rfc/bcp/bcp47.txt) standard. For more information about the BCP 47 format, refer to [Standard locale names](standard-locale-names.md).

Windows APIs have used BCP 47 locale names since Windows Vista. There are other locale representations, however; some of which are discussed below.

## LCID

Before Windows adopted IETF BCP 47 locale names, the [[MS-LCID]: Windows Language Code Identifier (LCID) Reference](/openspecs/windows_protocols/ms-lcid/70feba9f-294e-491e-b6eb-56532684c37f) was used to specify locales for Windows. LCIDs are also known as culture identifiers in the Microsoft .NET Framework environment.

Note that LCIDs are being deprecated, and implementers are strongly encouraged to use newer versions of APIs that support BCP 47 locale names instead. Each LCID can be represented by a BCP 47 locale name, but the reverse is not true. The LCID range is restricted and unable to uniquely identify all the possible combinations of language and region.

### LCID examples

LCIDs can identify neutral locales (a language without any region-specific information), specific locales (a language with a regional variant), and locales with alternate sort (for languages that have multiple methods of [sorting](sorting-and-string-comparison.md) data).

|LCID |Language tag |Type |
|---------|---------|---------|
|0x00000075 |haw |Neutral locale |
|0x00000409 |en-US |Specific locale |
|0x00010407 |de-DE_phoneb |Alternate sort for locale |

## POSIX

The [POSIX](../reference/glossary.md#posix) locale format, used on Unix, Linux, and other systems, is defined by [ISO/IEC 15897:2011](https://www.iso.org/standard/50707.html) and uses this format: **\[language[_territory][.codeset][@modifier]]**

The component parts are as follows:

- **language** is a two-letter language code from [ISO 639](https://www.iso.org/iso-639-language-codes.html)
- **_territory** is a two-letter country/region/subdivision code from [ISO 3166](https://www.iso.org/iso-3166-country-codes.html)
- **.codeset** is any pre-defined name for a character set or encoding identifier (for example, iso885915 or UTF-8)
- **@modifier** specifies an adjustment to the default locale behavior such as date/time/currency formatting or sorting method

The language code is the only mandatory part of a POSIX locale. Including a territory code is very common, as many languages are used in different countries/regions with regional variations.

The modifier part is not specified in any unified way. One common example is **@euro**. It was added to certain locales in the early 2000s when some countries/regions in the European Union changed from their national/regional currencies to the Euro.

### POSIX example

The POSIX locale de_DE.UTF-8@euro consists of the following parts:

- **de** for the German language
- **_DE** for Germany
- **.UTF-8** for the character encoding
- **@euro** to indicate that the locale is now using the Euro currency

## Comparative locale IDs

Here are some sample locales using the representations discussed above. Note that BCP 47 locales use a hyphen (-) to separate the language and territory codes, while POSIX compliant locales use an underscore (_).

|BCP 47 |LCID |POSIX compliant |Description |
|---------|---------|---------|---------|
|de-DE |1031 |de_DE |German for Germany |
|es-ES-u-co-trad |1034 |es_ES@traditional |Spanish for Spain, specifying the traditional sort order |
|sr-Latn-CS |2074 |sr_RS.UTF-8@latin |Serbian for Serbia, using the Latin script and the UTF-8 encoding |
