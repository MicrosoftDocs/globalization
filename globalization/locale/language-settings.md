---
title: Language settings
description: You should enable users worldwide to interact with your application by supporting various settings related to languages and input.
author: m-kauppinen
ms.author: v-mikau
ms.topic: conceptual #Required; leave this attribute/value as-is.
ms.date: 01/10/2023

---

# Language settings

Language is one of the most critical factors in how people communicate, relate, and operate. This means that any system should enable users to interact with the system in their preferred language. This is made possible by globalization of the system. Most operating systems today support at least one aspect of the hundreds and even thousands of languages and their variants that exist. This support includes user input and support for language rules like spelling and grammar.

When implementing the language settings for your application, it is important to keep in mind that users might want to interact with applications in languages other than the system’s default language. For example, many people want their operating system to use English as the default language, because it is so widely used for international working. But some of them have another language as their native language, and they want to add that language to the system for spellchecking emails written in that language. Or they might be learning Japanese, and they want the system to support writing with kana and kanji. There are numerous scenarios and a well-designed system should support as many as possible.

The different variables of a language that your users should be able to set include the following:

- [User interface language](ui-language.md)
- [Typing settings](typing-settings.md), which includes support for different keyboard layouts, text prediction, and additional settings, such as composing ideograms using dedicated input devices
- [Handwriting settings](handwriting-settings.md), which includes support for handwriting on a touchscreen device
- [Speech settings](speech-settings.md), which includes support for voice recognition and text-to-speech (TTS)
- [Proofing tools](dictionaries-spelling.md)
- [Collation, sorting, and string comparison](sorting-and-string-comparison.md)

Language settings are closely related to regional settings. Regional settings include:

- [Numbers](number-formatting.md): For example, how are numbers, including currencies, formatted.
- [Calendars, date, and time](date-time-formats.md): For example, how dates are formatted, what kind of time zones are used, and which day starts a new week.
- [Postal address formats](addresses.md)
- [Telephone number formats](telephone-numbers.md)
- [Units of measurement](measurement-units.md)
- [Punctuation conventions](../internationalization/punctuation-separators.md)
