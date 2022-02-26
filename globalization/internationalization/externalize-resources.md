---
title: Externalize localizable resources
description: Localization requires strings and other localizable resources to be separated from code and non-localizable resources (externalized).
---

# Externalize localizable resources

## Separate localizable and non-localizable resources

## Avoid repurposing strings

Developers with a mindset for efficiency may be tempted to use the same string for multiple purposes.
Reusing a string falls apart in a localized product because the context where a string is used is different.
If the string isn't separated for each use, it may not be possible to provide a single translation that works for all uses of that string.
A compromise translation creates confusion or incorrect results for international users.

A word or phrase in the source language may have multiple meanings, and be understood in context.
WHen translated, however, different contexts may require a different translation to make sense.

Translation is typically priced by the word, so using multiple strings containing the same text may seem that it would increase the cost.
This isn't the case because modern translation systems use a translation memory (TM).
A translator's editor will suggest existing translations from the TM for similar or duplicate strings.
For high-confidence matches, it will automatically add the translation and flag it for review by the translator.
Reviewing is faster and lower cost than defining a new translation.

In many cases, a TM match is appropriate, but may need to differ depending on context.
In cases where the context demands a different translation, having the separate string allows the translator to provide the optimal translation.
Without a separate string, the translator is forced to make compromises that may be flawed for the context.
Contextual metadata for localizable resources (resource commenting) is important when the same term is used in multiple places.

## Provide context for localizable resources

Translation is never a word-by-word substitution.
The choice of words and the information a sentence or word needs to convey is highly dependent on the context where it's used.
A resource by itself isn't sufficient context for a translator to rely on.
You can’t assume that the translator is aware of the file name or things close by.
Modern resource formats and localization tools allow resource commenting.
Developers should provide extensive comments to provide context.

A resource comment should explain where a string appears in the user interface and what it relates to.
The comment can explain when and where the message is displayed to the user.
If the string contains technical terms or application jargon, the usage should be explained.

## Non-localizable text

Items used within an application to drive functionality shouldn't be exposed to localization.
When a string is used both internally in code and is also displayed to the user, the usage should be split into separate strings.
Define a separate "display name" string and expose the display name to localization.

### Extensible applications

Non-localizable text is common in extensible applications.
Identifiers such as class names, keywords, functions, and database table names fall into this category.
If such a string is localized, then scripts and extensions become incompatible between locales.
