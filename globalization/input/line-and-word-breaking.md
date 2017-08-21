---
title: Line and Word Breaking
description: Some languages don't indicate the distinction between words by using spaces, different guidelines must be followed to deal with these languages.
ms.assetid: 792a33f6-1e08-48e9-b7f4-9a845c0fb9c8
ms.date: 03/16/2016
---
# Line and Word Breaking

Along with Complex Scripts, word and line breaking add a special case when multilingual text is to be parsed or displayed.

Latin script follows some straightforward rules for world and line breaking, such as breaking a line at a space, tab, or hyphen. For languages like Thai and Khmer, words run together (with no space between characters that end a word and those that begin another word, as with Latin script). This makes word breaking in such languages a more complex process, since syntax rules require line breaking on word boundaries. Thus for languages like Thai and Khmer, word breaking is based on grammatical analysis and on word matching in dictionaries during text processing at run time. Other languages also have rules of their own.

Unlike most Western written languages, Chinese, Japanese, Korean, and Thai do not necessarily indicate the distinction between words by using spaces. Although the Thai language does not use spacing between words, it still requires lines to be broken on word boundaries.

For these languages, world–ready software applications cannot conveniently base line–breaking and word–wrapping algorithms on a space character or on standard hyphenation rules. They must follow different guidelines.

Take Japanese, for example. Japanese line breaking is based on the *kinsoku* rules–you can break lines between any two characters, with several exceptions. The first exception is that a line of text cannot end with any leading characters–such as opening quotation marks, opening parentheses, and currency signs–that shouldn't be separated from succeeding characters. The second exception is that a line of text cannot begin with any following characters—such as closing quotation marks, closing parentheses, and punctuation marks–that shouldn't be separated from preceding characters. The third exception is that certain overflow characters (such as punctuation characters) are allowed to extend beyond the right margin for horizontal text or below the bottom margin for vertical text.

### Line/Word Breaking in Win32

Many applications deal mostly with plaintext–text that is all in the same typeface, weight, color, and so on. Such applications have traditionally displayed text using standard Win32 display entry points (TextOut, ExtTextOut, TabbedTextOut, and DrawText) to write text to a window, and the GetTextExtent family of functions to measure line lengths. In Windows 2000 and Windows XP, the standard entry points—as long as standard controls have been extended to support display of multilingual Unicode text and complex scripts, to display vertical text, and to handle special rules regarding line breaking and word breaking. In general, this support is transparent to the application itself, so properly designed applications require no changes to support complex scripts through these interfaces. Finally, your line-breaking is safe when you use standard multiline edit control.

Applications that apply more complex formatting rules to the output may do it using Rich Edit control. This component, among other multilingual features, offer language-sensitive line-breaking mechanisms. And finally, Uniscribe provides the supports for line breaking at word boundaries through ScriptBreak for those who build complex formatted output in their own code.

### Line/Word Breaking in .NET Framework

Text input, output, and display in Web content has been made a lot easier because HTML rendering in Internet Explorer is handled by the Trident module (mshtml.dll), which is one of the Uniscribe clients. All support for different input languages and complex scripts is provided to Web–based pages automatically and transparently, as long as Unicode encoding (either UTF-8 or UTF-16) is used. For Web content within the .NET Framework, system support hides all implementation details for Microsoft Windows Forms and for other .NET applications.

Another essential aspect of a globalized application is its ability to display the correct font. Thanks to the evolution of font technology, enabling support for varying fonts has become a more manageable task.


