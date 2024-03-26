---
title: Contextual metadata
description: Developers should add metadata to resource files to provide context to translators.
ms.date: 3/26/2024
author: jowilco
---

# Contextual Metadata

When translating string resources, it is often difficult for translators to understand how a string will be used, or how placeholders in the string will be populated, such that they can translate the string correctly. If mistranslated strings are identified during testing, additional time will be needed to fix the translation. Worse, when mistranslated strings are included in the delivered product, they will affect the users’ perception of the quality of the product.

Some resource file formats support adding metadata or comments to each resource. This contextual metadata is a valuable tool for providing guidance to the translators.

Contextual metadata should not be a substitute for incorrect or misleading source text (source quality). Where possible, the source text should use full sentences and unambiguous word choices:

- You should verify spelling and grammar before sending strings to translators. This simple step can reduce questions from translators and additional rework.
- Terminology should be used consistently throughout the application. You might have variants of terms, for example, a short name and a long name, but you should always use the terms consistently.
- In English, words and phrases can have multiple meanings. For example, “email” could be a noun or a verb, and “light” could be the opposite of “heavy” or “dark”. Where possible, consider alternative word choices when these types of words or phrases are used.
- Noun strings, also known as *noun clusters* or *noun chains* (consecutive nouns that modify the final noun) are commonly used in English. For example, “Node Color Field” could mean, “field for the color node”, “node field for the color”, or “field for the node’s color”. Other languages require the prepositions and articles that have been removed in English. It is often easier for English users to understand the meaning of a string to use the prepositions and articles, even if that means a longer string than the noun string version.
- [Concatenating strings](concatenation.md) should be avoided. String fragments are very difficult to translate correctly, and assembling string fragments into sentences is problematic when the sentence structure in the target language doesn’t match the source language.

It is best practice to add comments while the strings are being authored. For example, in the noun string case, you might not remember why the words “Node Color Field” was chosen when the string was created, and you might need to review the code to understand where the string is used before being able to answer questions from translators.

Contextual metadata for strings can be organized into four groups:

- Context for the text of the string
- Context for placeholders and variables within the string
- Metadata defining requirements
- Metadata for use with translation management tools

Here is an example from a .resx file showing contextual metadata in a <comment> element.

```resx
…
<data name="WorkOrderRequired">
  <value>{0} is required.</value>
  <comment>{Placeholder='{0}'} Placeholder '0' is an entity display name for the work order</comment>
</data>
…
```

## Metadata that provides context for the text of the string

Providing comments for how to translate a string can be very helpful to translators. Examples of this type of contextual metadata include:

- Where is the string used? This might include the location where the string will appear on screen (menu item, title, button) and how the string will be used (noun, verb).
- Under what conditions does the string appear? It can be helpful to include steps to replicate the string within the UI so that the translator can see the string in context.
- Does the translation need to match or be different?
  - The translation might need to match a string used elsewhere in the application or match a string used in the operating system or in a third-party application.
  - Is the string used in a list of strings where every item must be different? For example, you might have a list of actions that include “check” and “verify”. Both words might be translated as “vérifier” in French but must be translated as two distinct words in this list.
- Is there terminology or abbreviations in the string? The translation process includes a step for isolating terminology and abbreviations. However, if a term or an abbreviation is only used once, it is better to add context where it is being used.

## Metadata that provides context for placeholders and variables within the string

Most programming languages have methods or functions that allow programmers to insert variables into specific locations in strings. The specific locations where variables can be inserted might be called *format items*, *replacement fields*, *format elements*, *format specifiers*, or similar. For this section, the generic term *placeholder* will be used. It is best practice to add comments describing how placeholders in strings will be used.

There are several types of placeholders, depending on the programming language or framework.

- Position specifier. For example, `%2` indicates that the second argument in the list of arguments will be inserted at this location.
- Type specifier. For example, `%s` indicates that a string variable is expected while `%d` indicates that a decimal integer is expected.
- Named placeholders. For example, `{myvariable}` indicates that the value of the `myvariable` argument will be inserted at this location.

Neither position specifiers nor type specifiers provide context about the contents of the variables. Consider adding the following information in your comment:

1. A description of the variable that will be inserted at each placeholder.
1. An example of each variable.

For the type-specifier style of placeholders, if multiple placeholders are used, the translators must use the same ordering as the source string. This can be challenging for some languages as word order can be different from the source language.

For the position-specifier style of placeholders, the translators can change the order of the placeholders within the string. However, without context, it can be very difficult to determine how each placeholder will be used.

You should add comments even when the named style of placeholders is supported. While the variable name might be meaningful for the engineer who is familiar with how the code will use the string, that might not be the case for the translator. Adding a description and an example of each variable will help ensure that the translator can create the correct translation.

See [Strings and variables](message-formatting.md#strings-and-variables), for more information about using strings with variables.

## Metadata that defines requirements

If you have requirements for how a string should be translated, you can use comments to provide guidance to the translators. For example:

- Length restrictions – you might want to specify the maximum or minimum number of characters that can be used.
- Invalid characters – you might want to specify that only certain characters can be used. For example, a username might be limited to the letters a-z. If a string is providing an example containing a username, if the translators want to provide a sample username that is localized they will need to use a username that meets the a-z letter restriction.

## Metadata for use with translation management tools

In partnership with your localization vendor and the computer-aided translation or translation management system, you might be able to use contextual metadata to specify behavior for how strings will be managed. One typical example is being able to *lock* strings so that translators are not able to translate them; in other words, the source string will be used as the target string.

## Choosing when to add context

While it is often best practice to add contextual metadata to most strings, you should focus on adding contextual metadata where it adds value. Your goal should be to provide translators enough information to reduce ambiguity when choosing how to translate a string. Conversely, adding metadata where the context is obvious might be redundant. Full sentences tend to be easier to translate when compared to short strings or single words, so focus on the short strings or strings containing variables when choosing whether to add contextual metadata.
