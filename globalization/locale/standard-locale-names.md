---
title: Standard locale names
description: This article describes the standard structure of locale names.
author: m-kauppinen
ms.author: v-mikau
ms.topic: conceptual #Required; leave this attribute/value as-is.
ms.date: 02/13/2023

---

# Standard locale names

[IETF BCP 47](https://www.ietf.org/rfc/bcp/bcp47.txt) is the standard that defines the most-commonly used format for specifying a locale. This format is used by Windows and many other environments, including C#, Java, Javascript, ICU, HTML &lt;lang&gt;, etc.

A locale using the BCP 47 format is defined by a primary language tag and optional subtags as follows:

|Tag type |Composition |Notes |Mandatory / Optional |
|---------|---------|---------|---------|
|[ISO 639](https://www.iso.org/iso-639-language-codes.html) language tag |2 letter code from ISO 639-1 (2002) **OR** 3 letter code from ISO 639-2 (1998), ISO 639-3 (2007), or ISO 639-5 (2008) **OR** 5-8 letters and registered through the BCP 47 process. |Recommended: lowercase. |Mandatory |
|Extended language subtags (extlang) |Up to 3 subtags, 3 letters each, separated by hyphens. |Recommended: lowercase. Note that for all existing language + extlang combinations there is already an equivalent language tag (for example, zh-yue / yue). Only a few of these are defined. |Optional |
|[ISO 15924](https://unicode.org/iso15924/iso15924-codes.html) script tag |3 letters. |Recommended: Title Case. |Optional |
|[ISO 3166-1](https://www.iso.org/iso-3166-country-codes.html) alpha-2 region subtag **OR** [UN M49](https://unstats.un.org/unsd/methodology/m49/) region subtag |2 letters or 3 digits, respectively. |Recommended: UPPERCASE. |Optional |
|Variant subtag |5-8 letters or 4 characters starting with a digit, separated by hyphens. |Recommended: lowercase. Variant subtags describe additional distinctions, such as dialects or spelling reforms. They are registered with IANA and not associated with any external standard. |Optional |
|Extension subtags |1 character (that cannot be the letter x) and a hyphen, followed by 1 or more subtags of 2-8 characters each, separated by hyphens. |Recommended: lowercase. |Optional |
|Private-use subtag |The letter x and a hyphen, followed by subtags of 1-8 characters each, separated by hyphens. |Recommended: lowercase. Note that private-use subtag behavior is not defined other than as part of any agreement between parties using the private-use subtag. |Optional |

## Tag examples

|Example  |Corresponds to  |Explanation  |
|---------|---------|---------|
|de |German |A primary language tag with no additional qualifiers. |
|zh-yue-HK |Cantonese for Hong Kong |A primary language tag, an extended language subtag, and a region subtag. Equivalent to yue-HK. |
|sr-Latn |Serbian, written using the Latin script |A primary language tag and a script subtag. |
|de-AT |German for Austria |A primary language tag and a region subtag. |
|ca-ES-valencia |Valencian for Spain |A primary language tag, a region subtag, and a variant subtag. |
|de-DE-u-co-phonebk |German for Germany, using phonebook ordering |A primary language tag, a region subtag, and an extension subtype. In this example, the extension subtype is defined by Unicode’s Common Locale Data Repository (CLDR) project (u-), and indicates a collation type, or sort order, (co-) of phonebook. |
|de-DE-x-microsoft |German for Germany with a specific use within Microsoft |A primary language tag, a region subtag, and a private-use subtag. Note that private-use subtag behavior is not defined other than as part of any agreement between parties using the private-use subtag. |

## Tag changes

Developers should keep in mind that ISO 639 language tags  can change over time. A few examples are listed below:

- The Yiddish “ji” changed to “yi” in 1989.
- The Indonesian “in” changed to “id” in 1989.
- The Hebrew “iw” became “he” in 1989.
- The Serbo-Croatian “sh” was replaced by Serbian “sr” and Croatian “hr” in 2000.

Region subtags have changed as well. For example, the country of Serbia and Montenegro was assigned the ISO 3166-1 alpha-2 subtag "CS". In 2006, "CS" was deleted from ISO 3166-1 and ISO 3166-2, and the new countries were assigned the subtags “ME” (Montenegro) and “RS” (Serbia).
