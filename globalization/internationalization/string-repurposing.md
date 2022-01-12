---
title: String repurposing
description: Developers with a mindset for efficiency may be tempted to use the same string for multiple purposes. This practice falls apart in a localized product because the context where a string is used is different, and may require different terms in another context.
---

# String repurposing

Developers with a mindset for efficiency may be tempted to use the same string for multiple purposes.
This practice falls apart in a localized product because the context where a string is used is different, and may require different terms in another context.
Avoid repurposing strings.

Because translation is typically priced by the word, it may seem that it would increase the cost of localization to use multiple strings containing the same source language text.
This is not the case because modern translation systems use a translation memory, and will suggest existing translations for the duplicate strings to the translator.
In cases where the same text in the target language is suitable for a given context where the string is used, the translator accepts the suggested translation and the repetition is not charged or charged at a lower rate.
In cases where the context demands a different translation, having the separate string allows the translator to provide the optimal translation, and not a compromise translation for the various contexts.