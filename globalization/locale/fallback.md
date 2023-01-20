---
title: Fallback behaviors
description: When a global application does not have full support of a given locale, it can fall back to an appropriate supported locale.
author: m-kauppinen
ms.author: v-mikau
ms.topic: conceptual #Required; leave this attribute/value as-is.
ms.date: 01/20/2023

---

# Locale fallback

Despite best efforts, sometimes an operating system, application, or piece (item?) of content cannot offer the user the language and/or related parameters they are expecting or have requested. The user might find that their desired language is not available at all, or that only some parts of the system, application, or content are presented in that language. When this happens, there must be a mechanism in place for selecting the language that is presented instead of the user’s desired language. This replacement language is referred to as a fallback locale.

When a fallback locale is needed, the concept of language distance comes into play . The idea is to match languages or locales according to “closeness” data, offering the user the closest available language based on the acceptable languages they have specified. For more information, see [Unicode CLDR - Language Distance Data](https://cldr.unicode.org/development/development-process/design-proposals/language-distance-data).

Although language distance is a practical approach for developers, there needs to be an extra layer of geopolitical validation.
