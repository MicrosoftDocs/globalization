---
title: Non-localizable text
description: When implementing functionality and externalizing resources, take care to separate localizable text from non-localizable text.
---

# Non-localizable text

Items used within an application to drive functionality should not be exposed to localization.
If a string value is used both internally in code and is also displayed to the user, the two usages should be split.
Define a separate "display name" and expose the display name to localization.

## Extensible applications

Elements of an extensible or script-able applications are not localizable.
Identifiers such as class names, keywords, APIs, table names, and so on fall into this category.
If such a string is localized, then scripts and extensions become incompatible between locales.
