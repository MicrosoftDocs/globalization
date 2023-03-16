---
title: Locale fallback
description: When a global application does not have full support of a given locale, it can fall back to an appropriate supported locale.
author: m-kauppinen
ms.author: v-mikau
ms.topic: conceptual #Required; leave this attribute/value as-is.
ms.date: 01/20/2023

---

# Locale fallback

Operating systems and applications might not offer users full support for all combinations of language, country, region, or script. The user might find, for example, that their desired language is not available, their keyboard layout is not supported, or numbers are formatted differently from what the user would expect. When this happens, there is a mechanism in place for selecting what is presented instead of what the user would prefer. This mechanism for this replacement is implemented by the concept of a “fallback” locale. Instead of using the requested locale, the system or application will resolve the requested locale to a locale that is supported.

It is important to note that no system for implementing fallback is perfect or infallible. If you speak Arabic but a given application is not available in Arabic, the system might offer you a commonly available language such as English or French instead. But you might not know either of those. An "appropriate" fallback locale might not exist for you, and the system doesn't necessarily have a way of knowing this based on the language, script, country, or region settings you have selected.

In an ideal world the offered fallback locale is as "close" to your preferred one as possible. But "closeness" is relative. A French speaker in Canada might be happy to have their UI use the variant of French used in France - but France uses the AZERTY keyboard layout, while Canada uses QWERTY.

A system implements fallback the best it can because it must offer some locale to the user. But even from these two examples we can see selecting the right fallback locale is not simple. The offered fallback locale should be the best fit for as many users as possible. But this doesn't mean it will be a "good" solution for some or all of them. There are many different options for implementing fallback, some of which are discussed below.

## Modifying the default fallback

The default fallback locales provided by APIs might not be sufficient for your organizational needs. In this case you might want to override or extend the default fallback behavior described in the following sections.

## Unicode fallback options

### International Components for Unicode (ICU)

ICU is a set of C/C++ and Java libraries that provide Unicode, internationalization, and globalization support. ICU provides a set of locale-sensitive services such as number formatting, resource management, and text manipulation. A locale object in ICU can be constructed for any valid [BCP 47](https://www.ietf.org/rfc/bcp/bcp47.txt) locale and there is a default locale object that might be the default locale of the operating system (C++) or Java Virtual Machine (Java).

When using these locale-sensitive services, ICU will attempt to resolve the requested locale to a valid locale via the following steps:

1. If present, the variant code is removed.
1. If present, the country code is removed.
1. If present, the script code is removed.

If there is no match for the language code, ICU will attempt to use the default locale.

### Unicode Common Locale Data Repository (CLDR)

CLDR has proposed using “[language distance data](https://cldr.unicode.org/development/development-process/design-proposals/language-distance-data)” to improve the user experience when compared to the truncation algorithm that ICU currently uses. By using the distance between pairs of locales, an implementation could choose a more appropriate locale. For example, if es-MX (Spanish for Mexico) was requested, es-419 (Spanish for Latin America) might be a closer match than es (generic Spanish, presumably for Spain) which would be returned using ICU’s truncation algorithm.

## C# and culture fallback

C# uses the CultureInfo class to manage locale-specific functionality and it can be initialized using a BCP-47 language tag ([RFC 4646](https://www.rfc-editor.org/rfc/rfc4646) and LCID are also supported). A culture that is associated with a language and a country/region is called a “specific” culture. A culture that is associated with only a language is called a “neutral culture”. The invariant culture is culture-insensitive and can be initialized using an empty string.

The cultures have a hierarchy in which the parent of a specific culture is a neutral culture, the parent of a neutral culture is the InvariantCulture, and the parent of the InvariantCulture is the invariant culture itself. The parent culture encompasses the set of information that is common among its children.

### Resource fallback in the .NET Framework

If the resources for the specific culture are not available in the system, the resources for the neutral culture are used. If the resources for the neutral culture are not available, the resources embedded in the main assembly are used. For more information, refer to [Culture fallback scenarios](/dotnet/core/extensions/localization) and [Resources in .NET apps](/dotnet/core/extensions/resources).

## Java and locale matching

Java supports two mechanisms defined by [RFC 4647 Matching of Language Tags](https://www.rfc-editor.org/rfc/rfc4647): filtering and lookup. Java’s Locale class supports a LanguageRange, which can define one or more locales which match specific requirements. LanguageRange could specify a language (“de” – German), a specific locale (“de-CH” – German for Switzerland), or a country/region (“*-CH” – any language in Switzerland). Filtering returns the locales that match the LanguageRange, while lookup returns the best match for a locale based on the locales defined in the LanguageRange.

### Resource fallback in Java

ResourceBundle.getBundle will attempt to load a resource bundle that has a name that closely matches the base name + attribute values of the specified locale. If there is no direct match, attribute values are removed in the following order until a match is found:

1. Language, script, country, and variant
1. Language, script, and country
1. Language and script
1. Language, country, and variant
1. Language and country
1. Language

If no matching resource bundle is located, the same steps are used for the current default locale. If no matching resource bundle is located for the default locale, then the base name is used.

Note that there are special cases for Chinese and Norwegian.

- For Chinese, if an empty script value is supplied, “Hans” is assumed for China (“CN”) and Singapore (“SG”), while “Hant” is assumed for Hong Kong SAR China (“HK”), Macau SAR China (“MO”) or Taiwan (“TW”).
- Java treats “no” as a synonym for Norwegian Bokmål (“nb”); however no-NO-NY will be resolved to nn-NO (Norwegian Nynorsk).
