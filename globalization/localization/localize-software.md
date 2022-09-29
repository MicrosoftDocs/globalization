---
title: Localize software
description: Software and content localization each have their particular characteristics that drive different localization strategies.
author: v-williamsw
ms.author: v-williamsw
ms.date: 01/01/2022
--- 

# Localize software

When you design and build your software product, you need to address in advance the problems that might arise in localizing the product for other markets. Here are some things to consider:

- making it straightforward for translators to know and receive what content should be translated
- coding characters and strings that are compatible with th the character set used in target regions
- not persisting dates and times in a format that might vary by region
- not persisting numeric values in a format that might vary by region
- allowing room for expansion and contraction of the user interface for translated strings that are longer or shorter than the source strings
- researching that your user interface doesn't include elements that might be confusing or inappropriate to some cultures

## Separating your code from your translatable strings

Not all your material should be translated. You obviously don't want your executable code translated, since the compiler is expecting a programming language, not a human language. However, your code contains user-visible elements that you do want translated. These elements require localization:

- Menus
- Notifications and error messages
- Dialog boxes
- Prompts
- Tooltips
- Images
- Sounds
- Toolbars
- Status bars
- Constants

You don't want to leave the decision of what to translate in your product up to the translator. The translator isn't expected to know what is executable code and what is an element that should be translated. The translator could easily break your code by removing or altering a program character. Best to send the translator only what needs to be translated. Some of what you do send to the translator can be marked as "Do not translate" in the translation memories or terminology lists.

You can separate strings that should be translated by putting them in resource files. For Windows software, this resource repository can be Windows resource files, .NET assembly files, or a database when dealing with Web content. Because resource files don't require recompiling of source code, developers have used resource repositories to store resources referenced in one or more places in their code. This benefit actually adds complexity to what from a localization perspective should be a resource file containing only resources that need localization. Your developers should store strings that need to be translated in different resource files from those resources that shouldn't be translated.

This approach of using resource files solves another challenge: It avoids the hard-coding of strings, constants, and characters. Hard-coding forces translators to do some translation in source code files, a difficult and risky practice.

If developers want to use resource repositories for non-translatable content like functional resources (registry keys, function calls, and strings communicated between components) or debug resources, they should use separate repositories from the repositories for the translatable content. Otherwise you run the risk of translators translating strings that don't need to be translated. Or worse, translating things like command string names (for example, "Open") which will no longer work. [Willie: Can we refer here to the "Isolate localizable resources" article?]
[More Willie: The ASP.NET localization documentation says you should have "A set of resource files (.resx), one file for each language, that stores localized text." It says you should take "en-US" resource file and make copies for the target languages, e.g., if the en-US file is named translatable_strings.resx, you would make a copy of it called translatable_strings_fr_FR.resx for the French locale. Then when you have translated the strings, you'd rename that file back to translatable_strings.resx (so references to it from the code would still work). This translatable_strings.resx that is the French version would be part of the package delivered to you by the LSP. Should we say there should be language-specific versions of the resource files? I guess the translator could just translate the strings directly in the en-US .resx file and skip the renaming step.]
[One More Willie: Should we talk about the "satellite assembly" model, there the different language resource files are "satellites" around the non-localizable execution code hub?]

## String handling

Your coding of characters and strings is a central focus of globalization. Each culture or region may use different characters and character sets. These characters might not be supported at all, or there could be search, sort, and compare problems. The general solution for characters and strings is to use Unicode, which represents UTF-16 code units. Prior to Unicode, there were many different character encodings for identifying a character. These encodings didn't cover all languages, and within languages didn't cover all the letters, punctuation, and symbols. This omission was true even of English, and was especially true for pictographic languages like Japanese. Different encodings could have the same identifier for different characters, and could use different identifiers for the same character. Unicode solved both problems: it has a consistent mapping and it covers almost all characters in all languages.

Unicode can address more than 1.1 million code points. The default 16-bit encoding allows for these code points to be distributed across 17 planes. Each plane can address over 65,000 characters. The characters in Plane 0 are used to represent most of the world's written scripts, characters used in publishing, mathematical and technical symbols, geometric shapes, basic dingbats, punctuation marks, and some emoji. Coding your product with Unicode ensures portability across languages. [Willie: The next-to-last sentence is lifted from the "Encoding overview" article. Should I reword it? Maybe remove the whole concept of "plane" as well?]

When you deliver your translatable strings to the LSP for translation, you should require that they maintain the encoding. For product content that is delivered in various file formats, encoding is more of an issue. The CAT tool that the LSP uses to restore the translated strings to their original file format might have a codepage selector in which they can select Unicode. This could be Unicode (UTF-16), Unicode (UTF-8), or whatever they want for rendering the characters in their locale. [Willie: I'm not sure if the translator needs to worry about the encoding for the strings delivered in resource files for software translation. Maybe for that the encoding will stay as Unicode. They don't need to back convert the file to its original format.] [Willie: Also, should we reference the "Strings" section of the "globalization" article in the .NET documentation? (https://learn.microsoft.com/en-us/dotnet/core/extensions/globalization#strings)? Or "String handling for localizability"? (https://review.learn.microsoft.com/en-us/globalization/localizability/string-handling?branch=main)]

## Date and time

Because date and time formats can differ, depending on the locale, you need to be careful with them. The date time format of the United States, when deserialized in another locale, might throw an error or produce a different date. For example, consider the following two dates, serialized in the United States: January 9, 2022 and August 18, 2022. When these dates are parsed by using the conventions of the English (United Kingdom) culture, the first date is wrongly interpreted as September 1, and the second fails to parse because the Gregorian calendar doesn't have an eighteenth month. To avoid this problem, you should never persist date and time data in a format that can vary by locale. You can instead store the date and time in a resource file, and the resource file can have a locale identifier that will help translators set the correct date and time format.
[Willie: Should we reference the "Handle dates and times" section of the "Globalization" article in the .NET documentation?]

## Numeric values

Numbers can be treated differently in different locales. For example, the United States uses a period as a decimal separator, whereas France uses a comma. As with date and time, you should never persist numeric values in a format that can vary by locale. You can, instead, store these numeric values in a resource file that has a locale identifier. Currency values are a special case. Because it's tied to the currency unit, it's locale-independent. However, if the displayed value's formatted string includes the currency symbol, it will throw an error if it's deserialized in a locale that uses a different currency symbol. [Willie: Not sure if description of storing numeric value in a resource file is correct. Same for Date and Time above.] 

## Adapting the user interface

Translated strings can take up as much as 30% more space than the source strings in some languages. Or they can take up less space. You should therefore arrange with the LSP for accommodation of space concerns. You could discuss space issues before delivery of resource files (and software) to the client. Or you could make it an iterative process where the translations get loaded into the UI and your developers adjust the UI accordingly. Sometimes this problem can be avoided with "stretch to fit" containers. Sometimes the layout needs a code adjustment. You should plan accordingly.

## Avoiding cultural confusion or impropriety

You should anticipate whether any of your UI design, control labeling, or images might be confusing or even offensive to any of your target locales. You might even consider offering a different UI layout for certain locales. For example, uses in some locales might prefer a sparse design, where others might be used to a busier layout, where lots of functionality is compressed into a page. It's worth it to research what the popular and successful product designs are in your target markets.

## Next steps
<!-- Add a context sentence for the following links -->
- [Managing terminology](managing-terminology.md)
- [Maintaining a translation memory](translation-memories.md)
- [Content localization](localize-content.md)