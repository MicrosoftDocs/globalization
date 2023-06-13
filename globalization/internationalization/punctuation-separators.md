---
title: Punctuation and separators
description: Understand punctuation and separator differences for localization.
ms.date: 06/13/2023
---

# Punctuation and separators

In addition to date/time and numeric separators, localizers need to be aware of punctuation rules and the use of separators in other languages. For example:

- French uses a space, ideally a non-breaking space to avoid pagination issues, before and after most punctuation.
- Spanish uses inverted question marks and exclamation marks at the beginning of interrogative and exclamatory sentences or clauses.
- Some Asian languages use full- and half-with punctuation, depending on the context.

Lists, especially when generated from data structures like arrays, lists, and sets, have additional complications. For example:

- Various style guides, both in American and British English, recommend or oppose the use of the serial (Oxford) comma for comma-separated lists.
- While comma-separated lists are common in English, semicolons can also be used as a list separator when the list items contain commas.
- Different list separators are used in other languages. Semicolons are often used when the decimal separator is a comma. Chinese and Japanese use the ideographic comma (、U+3001) to separate list items.
- Japanese uses different coordinating conjunctions depending on whether the list is finite (all items are specified) or contains other items that are not specified.

Guidelines for localization involving punctuation and separators:

- Don’t assume that words, clauses, and sentences are separated by spaces.
- Don’t assume that the punctuation mark used in one language is the same mark in another language. This is especially true for quotation marks and parentheses.
- Don’t concatenate punctuation. If you need to add punctuation to a string, either include the punctuation in the string or use a string that contains the punctuation with a parameter so that the localizer has full control over the punctuation mark and spacing.
- When generating lists from data structures, be aware of the grammar rules of the target language.
