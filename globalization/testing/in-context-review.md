---
title: In-context review (ICR)
description: In-context review (ICR) can be the key to ensure high quality localized and translated experience for international users.
---

# In-context review (ICR)

In-context review (ICR) can be the key to ensure high quality localized and translated experience for international users.
ICR means performing [linguistic validation](linguistic-validation.md) in the context of the running application.
For documentation, the reviewer uses the same presentation medium that user's see.
More problems can be observed when the linguistic validation is performed in the context of the user's experience, rather than at the resource level.

## How to perform in-context review

Linguistic reviewers should be provided the following resources:

* Access to the working localized application.

* Your product style guides and glossary.

* Product documentation in both the source language and the target language.

* An agreed format and facility for recording and reporting issues.
Issue reporting can be via access to the product's issue tracking system, spreadsheets, documents, or email.

* A guide to your localization issue taxonomy. For more information, see [Issue taxonomy](issue-taxonomy.md).

* Instructions for reaching as much of the user interface for an application as possible.
You may be able to use your existing written test scenarios to aid the reviewer.

* A product team member to work side-by-side with the reviewer to walk through the application.
The reviewer supplies language and cultural expertise, and the product partner provides product knowledge and familiarity.
The product partner will know the extent and workflow of an application and can quickly operate the UI to reach all areas of the product.

* If a working application can't be provided to the reviewer or some areas of the application are difficult to reach, the reviewer can work from screenshots.
Screenshots are often an artifact available from a product's testing process or automation.

## Problems found by in-context review

In addition to the linguistic aspects in the article [Linguistic validation](linguistic-validation.md), ICR can discover other important issues that may not be apparent when reviewing translated text in isolation.

Using [pseudolocalization](../methodology/pseudolocalization.md) ("pseudo") can reveal many of these potential problems before you reach ICR.
With pseudo, you don't need a target language expert and you review only once, not per-language.
Using pseudo and fixing the issues before you perform ICR can help make your ICR more efficient.
However, pseudolocalization isn't a replacement for ICR.
In-context review will find unique language and locale issues that won't be found in pseudo.

Possible issues to be found by in-context review:

* Untranslated text.

* Over-translated text.

* Mistranslation, possibly due to lack of contextual comments.

* Truncation: translated text that is cut off in the user interface due to its length.
Pseudolocalization will find many truncation issues, but it will miss cases where a specific translation exceeds the  growth factor supplied by pseudo.

* Clipping: Missing or partial characters due to characters that extend beyond the typical bounds.
Examples include diacritics, stacked diacritics, and characters with long ascenders or descenders.

* Improper word wrapping, word selection, or line breaking.

* Mirroring issues.

* String concatenation or order-dependent insertions. Concatenation in the source can result in grammatically incorrect sentences.

* Improper pluralization for the language.

* Improper list forms for the language.

* Culturally appropriate or inappropriate functionality.

* Missing locale-specific functionality. Examples include:
  * Missing sort by stroke order for Chinese.
  * Lack of local or international paper sizes for printing.
  * Lack of a means to represent the pronunciation of people's names.

* Problems with fonts or encoding.

* Incorrect sort order for the locale.

* Problems with the input or presentation of people's names.

* Problems with data formats. There can be issues with the presentation of numbers, dates, times, calendars, currency, addresses, telephone numbers, and so on.
