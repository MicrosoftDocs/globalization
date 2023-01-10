---
title: Language settings
description: Applications should follow the user's language setting in the operating system as a default, not the system language.
author: m-kauppinen
ms.author: v-mikau
ms.topic: conceptual #Required; leave this attribute/value as-is.
ms.date: 01/10/2023

---

# Language settings

Language is one of the most critical factors in how people communicate, relate, and operate. This means that any system should enable users to interact with the system in their preferred language. This is made possible by globalization of the system. Most operating systems today support at least one aspect of the hundreds and even thousands of languages and their variants that exist. This support includes user input and support for language rules like spelling and grammar.

When implementing the language settings for your application, it is important to keep in mind that users might want to interact with applications in languages other than the system’s default language. For example, many people want their operating system to use English as the default language, because it is so widely used for international working. But some of them have another language as their native language, and they want to add that language to the system for spellchecking emails written in that language. Or they might be learning Japanese, and they want the system to support writing with kana and kanji. There are numerous scenarios and a well-designed system should support as many as possible.

The different variables of a language that your users should be able to set include the following:

- User interface language (#56152)
- Typing, which includes support for different keyboard layouts, text prediction, and additional settings, such as composing ideograms using dedicated input devices (#75880)
- Handwriting, which includes support for handwriting on a touchscreen device (#75881)
- Speech, which includes support for voice recognition and text-to-speech (TTS) (#56153)
- Dictionaries and spelling (#56154)
- Collation, sorting, and string comparison (#56155)

Language settings are closely related to regional settings. Regional settings include:

- Numbers: For example, how are numbers, including currencies, formatted.
- Calendars, date, and time: For example, how are dates formatted, what kind of time zones are used, and which day starts a new week.
- Postal address formats
- Telephone number formats
- Units of measurement
- Punctuation conventions
