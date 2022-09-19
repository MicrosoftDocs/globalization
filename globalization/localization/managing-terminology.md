---
title: Managing terminology
description: Careful up-front planning around the terminology used in your product can help ensure high quality localization and translation.
author: v-williamsw
ms.author: v-williamsw
ms.date: 01/01/2022
---

# Managing terminology

Your product contains many terms that are specific to it, and whose translation you should control carefully. You use terminology lists (in the form of term bases or glossaries) to manage these terms. Some of these terms you want translated in a specific way; some you don't want translated at all. For example, product names are often not translated. Company names are almost never translated. Your terminology lists should be developed in collaboration between internal teams (marketing, software, documentation, and linguistic engineers) and external (LSP) teams. Like translation memories, they need to be curated. Terminology lists can be linked to TMs, giving all translators access to the same resources and reference material.

Like TMs, terminology lists have a standard XML interchange format, called TermBase eXchange (TBX). You can obtain the ISO 30042 TermBase eXchange (TBX) standard [here](https://www.iso.org/standard/62510.html/).

Here are some overall process recommendations:

- Stabilize source terms early and front-load your localization with translating those terms.
- Try as much as possible to automate your term extraction process (term mining). Consider the use of AI solutions.
- Use a centralized terminology management system that all stakeholders can use.
- Notify stakeholders of terminology changes. 

## The importance of establishing terminology early

As with other globalization aspects, terminology management should be established even if the product isn't initially intended to be localized. The sooner the terminology management process starts, including the translation of terms, the better it is for the quality of the product. Terms appear in many instances across all your different content types, so defining them early will minimize editing and translation rework and cost overheads.
 
New software products often bring along new technologies and brand-new terms that might not exist in any of the target languages. Establishing those terms early will improve product adoption and will help translators to get familiar with those new technologies and features.

## Term extraction

You should have developed a terminology list for your product before you begin the localization process. In fact, the terminology list will improve the clarity and consistency of the product itself, translations aside. Because the terminology list can be used by the UI developers, the documentation team, and the marketing term, there will be a consistent presentation in all these areas.

The list will be essential in the translation process. There are several approaches to extracting the terms for the list from your product. Your product designers, software developers, QA personnel, marketers, sales personnel, and writers can submit terms as candidates for the terminology list as they develop the product. Then terminologists can curate the list. The terminologists should work with the product managers to improve the terminology in the product. There are also tools for extracting terms from your software and documentation. These tools can have a linguistic approach, identifying the part of speech and even adding annotations. There are also tools that perform a purely statistical analysis, looking for things like how often the term appears. As with the manually developed terminology list, these entries will have to be curated by terminologists.

## Employing a centralized terminology management system

To avoid inconsistent terminology across products and product versions, you should have a centralized repository for all terms. This repository should be accessible and contributed to by all stakeholders: product managers, project managers, marketers, terminologists, engineers, QA, and translators themselves. The system could be as simple as a spreadsheet or webpage with terms. It could be an internally developed database/front end. It could be a commercial terminology management system. CAT tools, utilizing TBX for interchange, can automate storage of terms and enforcement of consistency. A common problem is that different translation projects of a product produce different translation of the same terms. A centralized management system can spot and flag these inconsistencies in time to correct them.

## Considerations for terminology changes

Terminology changes can have far-reaching effects. Consider the following effects of these changes:

- Scope: changing and retranslating terms will affect all types of content deliverables. All stakeholders must be informed of changes.
- Schedule: you'll need extra time to handle terminology changes.
- Cost: more changes bring more rework, and a higher cost.
- Quality: terminology changes may introduce inconsistencies and/or inaccuracies to your product.

## The importance of context

Words can have multiple meanings (that is, can be homographs) depending on the contexts in which they're used. For example, the word "address" in software can have several meanings. It's crucial that your terminology list contains metadata describing the context in which the term is being used. TBX allows you to add a wealth of metadata, including the following information:

- Part of speech (for example, "address" can be a noun or a verb, and the translation for usage as a verb is likely to differ from the translation for usage as a noun)
- Usage note (for example, is "address" indicating a location in memory, an email identifier, a network node identifier, a URL, or what?)
- Grammatical gender (for example, masculine, feminine, neuter, or other)
- Term type (for example, standard text, international scientific term, equation, abbreviation, many others)

This metadata, when presented to translators via the CAT tool they're using, can be indispensable. For example, supposing translators see the sentence "A program can fetch the current contents of the byte at a given memory address and it can store a given value into that byte." The CAT tool might fetch the following metadata from the term base (along with the source and target segments) and present it along with the suggested translation "addresse" to the translator:
```
<termEntry id="myterm">
  <descrip type="definition">A number specifying a location in memory where data is stored</descrip>
  <langSet xml:lang="en-US">
    <tig>
      <term>address</term>
      <termNote type="partOfSpeech">Noun</termNote>
    </tig>
  </langSet>
  <langSet xml:lang="fr-FR"> 
    <tig>
      <term>adresse</term>
      <termNote type="partOfSpeech">Verb</termNote>
    </tig>
  </langSet>
</termEntry>
```
When translators see the metadata "A number specifying a location in memory where data is stored," they can be confident that "addresse" is the correct translation for this term. 

## Translating terms

In addition to finding the right translation for what the term means or does, there are other considerations. For example, should it be translated at all? Should it not even be included in the target? Should the translation include more or less than the source, due to peculiarities of the target audience?

### Translation vs. transliteration

Transliteration is the process of converting written script into another written script; for example, from English (Latin) to Russian (Cyrillic) or Japanese (Katakana). Transliteration is used primarily to make a term easier to read and pronounce in the target language. Transliteration doesn't address meaning; it focuses entirely on the characters that make up each word. When you're localizing your content, transliteration might come into play for proper nouns. For example, if you're translating from English to Russian or Japanese, you might transliterate the proper noun so its pronunciation will come across to the reader. If a product contains example names for people, translators have the option of leaving the name unchanged, using a transliteration, using an equivalent (for example, Guillermo instead of William), or using a replacement (for example, Miki/美紀 instead of Michelle).

### Product names and key features: translate/transliterate/source

No rule governs the decision of whether to translate your product names. Some markets respond better to product names in their native language than others. Some don't. There are products that failed in target markets until they translated their product name, then succeeded after doing so. It's worth it to field-test the alternatives. You want your product names to be consistent across countries and you hope your markets will learn and value the product names. But above all you want customers to buy the products. For feature names, you don't want the name to be an impediment to users, so feature names are more likely to be translated. As with people's names, since product names and key features might be new words, and therefore clumsy to translate, transliteration might be an alternative approach.  

### DNTs

In addition to product names and people's names that we've discussed above, there are many things you might not want translated. For example, brand names, trademarks, and key features might stay untranslated, to promote visibility and consistency across markets. Company names usually aren't translated, though there are exceptions. College and university names usually aren't translated, but they're often transliterated. There are terms that can't be translated because there's no equivalent in the target language. New terms might have no target translation. For new terms or terms without an equivalent in the target language, you would want either to introduce a new term in the target, use an analogous term, or transliterate. The source language term might become the de facto standard in the target language (a loanword).

### Acronyms and abbreviations

Acronyms can vary in different languages because they usually follow the order of the words they expand to, or because the translation for the source is a difference word sequence. For example, the French equivalent acronym for "DTP" is "PAO" (from the translation "Publication assistée par ordinateur"). The abbreviations for single words can differ as well. For example, the abbreviation for the French word "gigaoctet" (French for "gigabyte") is "Go". The Microsoft Style Guides for different languages often include a list of abbreviations that are different that language. See [Microsoft Language Portal](https://www.microsoft.com/Language/StyleGuides?rtc=1).

### Excluded terms (vulgarities, sensitive terms)

Your content might have words in it that are taboo or that are too sensitive to be seen by the target audience. This problem should be reflected in the annotation of the term entry. If possible, you should provide a translation that omits the vulgar or sensitive words while retaining the meaning of the source term.

### Slogans/tag lines

Your product tag lines and slogans have been carefully crafted, usually by the marketing department. Slogans/tag lines are normally a candidate for transcreation—taking the intent of the source language tag line, capturing any areas of focus for the target market, and adding style (alliteration, idiom, allusion) from the target language. As you create term entries for crafted phrases, you should work with the marketers that created the originals, to get their approval for the transcreations. This approval should be indicated with an annotation for the term entry. 

## Next steps
<!-- Add a context sentence for the following links -->
- [Maintaining a translation memory](translation-memories.md)
- [Localize software](localize-software.md)
- [Content localization](localize-content.md)