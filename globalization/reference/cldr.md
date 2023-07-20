---
title: Common Locale Data Repository (CLDR)
description: Learn how CLDR provides standardized locale data for libraries like ICU, globalize.js, and .NET APIs.
ms.date: 06/13/2023
---

# Common Locale Data Repository (CLDR)

The [Common Locale Data Repository (CLDR)](http://cldr.unicode.org) is a standardized source of locale data that provides information like patterns for formatting dates, names for countries/regions in different languages, and calendar preferences.

While CLDR provides regional format and sorting information, it doesn't define the implementation. CLDR is used by libraries such as the International Components for Unicode (ICU), globalize.js, and .NET APIs. These libraries might not implement all parts of any particular CLDR release; however, CLDR can be a good reference to implement features that you require in your application that aren't supported by the libraries that you're using.
