---
title: Externalize localizable resources
description: Localization requires strings and other localizable resources to be separated from code and non-localizable resources (externalized).
---

# Externalize localizable resources
<!-- NOTE this article is not yet complete -->
<!-- Add paragraph about externalization of non-loc resources -->

## Separate localizable and non-localizable resources

## Avoid repurposing strings

Developers with a mindset for efficiency may be tempted to use the same string for multiple purposes.
However, while the same string may work in many places in the source language, the translation appropriate for one context may not apply in another context.
If the string isn't separated for each use, it may not be possible to provide a single translation that works for all uses of that string.
A compromise translation creates confusion or incorrect results for international users.

A word or phrase in the source language may have multiple meanings, and be understood in context.
When translated, however, different contexts may require a different translation to make sense.
One-word strings used in menus, buttons, or as insertions in formatted strings, can be a problem.
Words that are both nouns and verbs are a common source of issues in translation.
The word "Click" for example is both a noun and a verb, and the translation may differ for each usage.

Something as simple as "Yes" or "No" on a button may need different translation in context.
For example, in Japanese, "Yes" may be translated as はい (Yes) or 有効 (Effective or Enabled)and, and "No" may be translated as いいえ (No) or 無効 (Disabled).
If only a single resource is used to represent all uses of the word, the translation may not work everywhere it is used.

In cases where the context demands a different translation, having the separate string allows the translator to provide the optimal translation.
Without a separate string, the translator is forced to make compromises that may be flawed.

## Provide context for localizable resources

Translation is never a word-by-word substitution.
The information that a sentence or word needs to convey is highly dependent on the context where a string used.
A word or sentence by itself isn't sufficient context for a translator.
You cannot rely on your translators to know your product well.
Developers provide context for resources through resource commenting (sometimes call "contextual metadata").

A resource comment should explain where a string appears in the user interface and what it relates to.
The comment can explain the conditions under which the message is displayed.
If the string contains technical terms or application jargon, the usage should be explained.

If the string is a format string containing placeholders, it is particularly important to document the part of speech and meaning of each placeholder.
See [Message formatting](..\internationalization/message-formatting.md) for more detailed guidance on message formatting.

## Non-localizable text

Items used within an application to drive functionality shouldn't be exposed to localization.
When a string is used both internally in code and is also displayed to the user, the usage should be split into separate strings.
Define a separate "display name" string and expose the display name to localization.

### Extensible applications

Non-localizable text is common in extensible applications.
Identifiers such as class names, keywords, functions, and database table names fall into this category.
If such a string is localized, then scripts and extensions become incompatible between locales.
