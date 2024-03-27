---
title: Externalize localizable resources
description: Externalize localizable resources to separate them from code and allow for independent processing.
ms.date: 03/26/2024
author: jowilco
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-desc
  - ai-seo-date:03/26/2024
---

# Externalize localizable resources

Localizable resources are separated from code ("externalized") so that they can be independently processed without modifying a product's source code.

Some programming environments provide facilities to maintain source text in the code, extracting localizable text during the build or a separate process. Keeping the source text in the code can be a convenience for developers, but has some disadvantages. Changes to source text that are needed for correctness or localizability requires a rebuild and retest, which can be undesirable.

## Separate localizable and nonlocalizable resources

Keeping nonlocalizable resources separate from localizable resources lowers the risk of over-localization and can reduce the complexity of localization. Where using separate files can't be used, [contextual metadata](contextual-metadata.md) can be used to distinguish localizable from nonlocalizable resources. Some localization tools provide a formal mechanism for excluding selected resources from localization. Exclusion from localization might be specified by an attribute in the resource file schema, or a special notation used in comments. For example, a tool might recognize `{Locked}` in a resource comment to "lock" the string and prevent it's localization.

## Avoid repurposing strings

Developers with a mindset for efficiency might be tempted to use the same string for multiple purposes. However, while the same string might work in many places in the source language, the translation appropriate for one context might not apply in another context. If the string isn't separated for each use, it might not be possible to provide a single translation that works for all uses of that string. A compromise translation creates confusion or incorrect results for international users.

A word or phrase in the source language might have multiple meanings, and be understood in context. When translated, however, different contexts might require a different translation to make sense. One-word strings used in menus, buttons, or as insertions in formatted strings, can be a problem. Words that are both nouns and verbs are a common source of issues in translation. The word "Click" for example is both a noun and a verb, and the translation might differ for each usage.

Something as simple as "Yes" or "No" on a button might need different translation in context. If "Yes" and "No" are button labels in a message box or user prompt, the correct translation depends on exactly what the message says. If only a single resource is used to represent all uses of the word, the translation might not work everywhere it's used.

For example, in Japanese, "Yes" might be translated as :::no-loc text="はい"::: (Yes) or :::no-loc text="有効"::: (Effective or Enabled). "No" might be translated as :::no-loc text="いいえ"::: (No) or :::no-loc text="無効"::: (Disabled). Which translation is correct depends on the context.

In cases where the context demands a different translation, having the separate string allows the translator to provide the optimal translation. Without a separate string, the translator is forced to make compromises that might be flawed.

## Provide context for localizable resources

Translation is never a word-by-word substitution. The information that a sentence or word needs to convey is highly dependent on the context where a string used. A word or sentence by itself isn't sufficient context for a translator. You can’t rely on your translators to know your product well. Developers provide context for resources through resource commenting (sometimes called [contextual metadata](contextual-metadata.md)).

A resource comment should explain where a string appears in the user interface and what it relates to. The comment can explain the conditions under which the message is displayed. If the string contains technical terms or application jargon, the usage should be explained.

If the string is a format string containing placeholders, it's important to document the part of speech and meaning of each placeholder. For more information about message formatting, see [Message formatting](message-formatting.md).

## Nonlocalizable text

Items used within an application to drive functionality shouldn't be exposed to localization. When a string is used both internally in code and is also displayed to the user, the usage should be split into separate strings. Define a separate "display name" string and expose the display name to localization.

### Extensible applications

Nonlocalizable text is common in extensible applications. Identifiers such as class names, keywords, functions, and database table names fall into this category. If such a string is localized, then scripts and extensions become incompatible between locales.
