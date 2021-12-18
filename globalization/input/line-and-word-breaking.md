---
title: Line and word breaking
description: Some languages don't indicate the distinction between words by using spaces, different guidelines must be followed to deal with these languages.
ms.assetid: 792a33f6-1e08-48e9-b7f4-9a845c0fb9c8
ms.date: 03/16/2016
---
# Line and word breaking

Along with complex scripts, word and line breaking add a special case when multilingual text is to be parsed or displayed.

Latin script follows some straightforward rules for layout, such as breaking a line at a space, tab, or hyphen.
Chinese, Japanese, Korean, and Thai do not necessarily indicate the distinction between words by using spaces.
For languages like Thai and Khmer, word breaking is based on grammatical analysis and on word matching in dictionaries during text processing at run time.
Although the Thai language does not use spacing between words, it still requires lines to be broken on word boundaries.
Other languages also have word and line-breaking rules of their own.

For these languages, world–ready software applications cannot conveniently base line–breaking and word–wrapping algorithms on a space character or on western hyphenation rules.
They must follow different guidelines.

Take Japanese, for example. Japanese line breaking is based on the kinsoku rules: you can break lines between any two characters, with several exceptions.
The first exception is that a line of text cannot end with any _leading_ characters – such as opening quotation marks, opening parentheses, and currency signs – that shouldn't be separated from succeeding characters.
The second exception is that a line of text cannot begin with any _following_ characters — such as closing quotation marks, closing parentheses, and punctuation marks – that shouldn't be separated from preceding characters.
The third exception is that certain overflow characters such as punctuation are allowed to extend beyond the right margin for horizontal text or below the bottom margin for vertical text.

## Line and word breaking in Win32

Many applications deal mostly with plaintext: text that is all in the same typeface, weight, color, and so on.
Such applications have traditionally displayed text using standard Win32 display entry points (TextOut, ExtTextOut, TabbedTextOut, and DrawText) to write text to a window and the GetTextExtent family of functions to measure line lengths.
Since Windows 2000 and Windows XP, the standard controls have been extended to support display of multilingual Unicode text and complex scripts, to display vertical text, and to handle special rules regarding line breaking and word breaking.
In general, this support is transparent to the application itself, so properly designed applications using standard user interface controls require no changes to support complex scripts.
Finally, layout is safe when you use standard multiline edit control.

Applications that apply more complex formatting rules to the output may do it using Rich Edit control.
This component, among other multilingual features, offer language-sensitive line-breaking mechanisms.
And finally, Uniscribe provides the supports for line breaking at word boundaries through ScriptBreak for those who build complex formatted output in their own code.

## Layout in .NET

Text input, output, and display in Web content has been made a lot easier because HTML rendering is handled by the browser.
All support for different input languages and complex scripts is provided to Web–based pages automatically and transparently, as long as Unicode encoding (either UTF-8 or UTF-16) is used.
For Web content within the .NET Framework, system support hides all implementation details for Microsoft Windows Forms, WPF, and for other .NET applications.

Another essential aspect of a globalized application is its ability to display the correct font.
Thanks to the evolution of font technology, enabling support for varying fonts has become a more manageable task.
