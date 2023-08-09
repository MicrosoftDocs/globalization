---
title: Manage terminology
description: Careful up-front planning around the terminology used in your product can help ensure high quality localization and translation.
author: m-kauppinen
ms.author: v-mikau
ms.topic: conceptual #Required; leave this attribute/value as-is.
ms.date: 07/27/2023

---

# Manage terminology

All organizations use some kind of terms, whether general, industry-specific terms or ones specific to your company or product. You should plan for terminology management from the beginning of your project, even if you don’t know whether the product will be localized. Well-defined terms improve the consistency of your product as well as its documentation and marketing materials. Terms also help to establish your brand voice. And when the time for localization comes, a properly managed terminology database (termbase) becomes crucial. The sooner you have a terminology management process in place, including the localization of terms, the more it will help the development of the original product and save time and money with any localized versions. Early translation of terminology also improves the overall quality of the localized product. If all your important terms have correct translations "locked in" before the localization of the whole product starts, each translator working on the project won't need to create their own translations for terms, which would inevitably vary.

It's possible to have a bare bones termbase in something like a Microsoft Excel sheet that lists terms and their equivalents in other languages. But you get much better results using a dedicated terminology management solution that is integrated with computer-aided translation (CAT) tools and supports the standardized [TermBase eXchange (TBX) format](localization-file-formats.md). Such a solution lets you easily store all kinds of [contextual information and metadata](#what-to-include-in-your-termbase) for each term and share the termbase with other stakeholders.

## What to include in your termbase

You should consider including the following information per language or locale for each term:

- Definition: this is the absolute minimum requirement.
- Source/context: context is a critical aspect that affects localization.
- Taxonomy: how the term is classified or grouped in your company or product.
- Grammatical usage: for example, information about gender or part of speech.
- Date: when the term was created or modified.
- Author
- Examples of use: these are very helpful for translators.
- Exclusions: when the term shouldn't be used, and alternative spellings/terms that should not be used.
- Related terms
- Product applicability: especially when different product lines use different translations for the same English term.

## Term extraction

When you first build your termbase, using automated term extraction or term mining can be helpful. There are various tools and AI solutions for this purpose. After generating the initial list, it usually needs some manual cleaning and pruning by a terminology expert who works together with development team members to define and approve all terms that are selected for the termbase.

## Process recommendations

Here are some good practices for terminology management:

- Stabilize source terms as early as possible. Translate those terms as the first thing in the localization process. If your product includes some new terms that don’t have translated versions in your target languages, coining those terms early also helps translators to get familiar with the new technology or feature in question.
- A source term, as spelled, can refer to more than one concept. You should have separate entries in the terminology management system for these cases.
- Different source terms can sometimes be translated into a given language using the same localized term. Where possible and relevant, you should avoid this.
- Notify all stakeholders of terminology changes. When term changes do occur, remember to reserve some time for the localization of new and changed terms and the updating of all materials that use the older terms – including their translated versions. A termbase tool enables all stakeholders to access the updated terms as soon as they're available.

## Term localization

You should consider the following when localizing terms:

- Product names and key features: should each of them be translated, transliterated, or left as the source term? If your term is trademarked, will you need to trademark a translated equivalent?
- Fictitious names and/or names for examples: consider using names that are relevant for the target audience in any examples you have, instead of keeping English names, for example. The names should also be as inclusive as possible.
- Sometimes a given term might have to be marked as Do Not Translate (DNT). The most common reasons are branding or industry-specific terminology. For example, the name of the product or its key features might remain in English. Sometimes the market might prefer the “English” term even if an equivalent term exists in the target language.
- Abbreviations: how to handle these? Try to settle on a consistent approach to be used in all cases.
- Phrases or tag lines: if a tag line is an important part of your branding or marketing, its localization merits extra care.
