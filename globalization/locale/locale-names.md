---
title: Locale names and LCID deprecation
description: For those developers still using LCIDs, it is recommended to move to local names as they are more robust than LCID and can support many more markets.
---

# Locale names and LCID deprecation

In the modern and managed worlds developers have been using Locale Names (a.k.a., [IETF language tags,](http://en.wikipedia.org/wiki/IETF_language_tag) locale tags, language tags, culture tags, culture codes, [BCP 47](https://tools.ietf.org/html/bcp47) tags, ll-cc, “en-US”, et cetera) for some time, but in other contexts LCID (locale identifier) codes continue to be used.
For those developers still using LCID, it is recommended to move to locale names as they are more robust than LCIDs and can support many more markets.

## What is a locale?

A locale is a collection of features of the user’s environment that is dependent on language, country/region, and cultural conventions. The locale determines conventions such as sort order; keyboard layout; and date, time, number and currency formats.

## What is an LCID?

Up until Windows Vista, each [locale](/windows/win32/intl/locales-and-languages) supported by Windows had a unique [LCID](/windows/win32/intl/locale-identifiers): a 32-bit value that consists of a [language identifier](/windows/win32/intl/language-identifiers) and a [sort order identifier](/windows/win32/intl/sort-order-identifiers).
The LCID is a Microsoft-proprietary numeric identifier for the locale, and before Windows Vista the LCID was used to identify operating system-defined locales.
The NLS APIs in Windows support these predefined ids.

As many applications do not care about the differences between sort identifiers, many developers see the LCID as synonymous with the lower 16 bit language identifier (LID) portion.

## The deprecation of LCIDs

LCIDs no longer provide a unique identifier for all the locales supported on Windows.
The restricted range of the LCID makes it impossible to provide a unique identifier for each of the millions of language and region "locale" combinations that can be identified.

The deprecation of the LCID began with Windows Vista, when APIs were added to recognize BCP 47 tags.
Windows Vista also introduced custom locales, and those locales may not have an assigned LCID.
Requests for new LCIDs for those locales would use the [LOCALE\_CUSTOM\_DEFAULT](/windows/win32/intl/locale-custom-constants) or [LOCALE\_CUSTOM\_UNSPECIFIED](/windows/win32/intl/locale-custom-constants) identifiers.
LOCALE\_CUSTOM\_DEFAULT if they locale happens to be the user default locale, otherwise LOCALE\_CUSTOM\_UNSPECIFIED.

Prior to Windows 8, the Windows team would assign new LCID values for each new locale added to Windows.
However, starting with Windows 8, Windows started adding new locales that do ***not*** have a unique pre-assigned LCID value to identify them.
Those locales act much like the custom locales introduced in Vista, typically using LOCALE\_CUSTOM\_UNSPECIFIED.

Windows 8 also introduced the concept of a "transient LCID" for the LCID-challenged "no-LCID" locales that do not happen to have a preassigned LCID.
For some locales, Windows 8 will attempt to generate a "transient LCID" from a pool of reserved LCIDs.
Transient LCIDs are just there to satisfy the requirement that the API uses an LCID, but the actual transient LCID value you will get at runtime is essentially meaningless.
If you do anything with a transient LCID, it will very likely cause data loss.
There are only a handful of values reserved for use as transient LCIDs, and there are far more transient locales than there are transient LCIDs.
The transient LCIDs are handed out on a first-come-first-served basis when a user adds a transient locale to their Windows Language Profile.
A transient LCID can be re-assigned by the system at any time (such as when the user changes their Language Profile), and because it can mean a different locale for a different user and/or on a different system, it is transient and cannot be used as a durable identifier.

In Windows 10, Windows NLS expanded upon the transient concept to be able to recognize any well formed BCP-47 locale name presented to it.
Windows will then "construct" a locale from the best information available.
Those all share the LOCALE\_CUSTOM\_UNSPECIFIED LCID, unless they happen to be transient and get a random LCID assigned to them. With Windows 10, over half of the in-box locales are "no-LCID" locales, and many millions more are possible with the generous constructed locale capability.

## Adapting existing LCID-based code

For every API that accepts an LCID, there is generally an extended (_name_Ex) version of the API that accepts a locale name that should be used instead.
When you see the use of an LCID, the current documentation for that API will refer to the appropriate replacement API that uses a locale name.
