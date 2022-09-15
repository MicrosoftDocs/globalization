---
title: Managing terminology
description: Careful up-front planning around the terminology used in your product can help ensure high quality localization and translation.
author: v-williamsw
ms.author: v-williamsw
ms.date: 01/01/2022
---

# Managing terminology

[from "Localization Overview article; is it okay to reuse it?]
Your product no doubt contains many terms that are specific to it, and whose translation you should control carefully. You use terminology lists (also called term bases or glossaries) for these terms. Some of these terms you want translated in a specific way; some you don't want translated at all. For example, product names are often not translated. Company names are almost never translated. Your terminology lists should be developed by internal teams (marketing, software, documentation, and linguistic engineers) and external (LSP) teams. Like translation memories, they need to be curated. Terminology lists can be linked to TMs, giving all translators access to the same resources and reference material. 

Like TMs, terminology lists have a standard XML interchange format, called TermBase eXchange (TBX). You can obtain the ISO 30042 TermBase eXchange (TBX) standard [here](https://www.iso.org/standard/62510.html/).

## The importance of establishing terminology early

As with other globalization aspects, terminology management should be established even if the product isn't initially intended to be localized. The sooner the terminology management process starts, including the translation of terms, the better it is for the quality of the product. Terms appear in many instances across all your different content types, so defining them early will minimize editing and translation churn/cost overheads.
 
New software products often bring along new technologies, and hence brand-new terms that don't necessarily exist in any of the target languages. Coining those terms early will improve the product and will help translators to get familiar with those new technologies and features.

## Considerations for terminology changes

Terminology changes can have far-reaching effects. Consider the following effects of these changes:

- Scope: changing and retranslating terms will affect all content type deliverables.
- Schedule: you'll need to fit extra time to handle terminology changes.
- Cost: more changes bring more churn, and a higher cost.
- Quality: terminology changes may introduce inconsistencies and/or inaccuracies to your product.

Here are some overall process recommendations:

- Stabilize source terms early and front-load your localization with translating those terms.
- Try as much as possible to automate your term extraction process (term mining). Consider the use of AI solutions.
- Use a centralized terminology management system that all stakeholders can use.
- Notify stakeholders of terminology changes.

## Term extraction

You should have developed a terminology list for your product before you begin the localization process. In fact, the terminology list will improve the clarity and consistency of the product itself, translations aside. The list will be essential in the translation process. There are several approaches to extracting the terms for the list from your product. Your product designers, software developers, QA personnel, marketers, sales personnel, and writers can submit terms as candidates for the terminology list as they develop the product. Then terminologists can curate the list. The terminologists should work with the product managers to improve the terminology in the product. There are also tools for extracting terms from your software and documentation. These tools can have a linguistic approach, identifying the part of speech and even adding annotations. There are also tools that perform a purely statistical analysis, looking for things like how often the term appears. As with the manually developed terminology list, these entries will have to be curated by terminologists.

## The importance of context
Words can have multiple meanings (that is, can be homographs) depending on the contexts in which they're used. Consider these five uses of the word "address" in computer terminology:

|Term|Context|Part of Speech|French translation|
|----|---|---|---|
|address|To reference a particular storage location|Verb|adresser|
|address|A string that identifies a user so that the user can receive Internet email and typically consists of an account name, followed by the @ symbol, a host name, and a domain name|Noun|adresse|
|address|A unique identifier that identifies a network node to other nodes on the network|Noun|adresse|
|address|A number specifying a location in memory where data is stored|Noun|adresse|
|address|A path to a file on a network that can be a URL or a UNC path and that can contain a reference to a location within the file|Noun|adresse|

It's crucial that your terminology list contains the context in which the term is being used. The TBX standard provides a description field (\<*descrip*>) at the term entry level that can be used to give the context:
```
<termEntry id="myterm">
  <descrip type="definition">To reference a particular storage location</descrip>
  <langSet xml:lang="en-US">
    <tig>
      <term>address</term>
      <termNote type="partOfSpeech">Verb</termNote>
    </tig>
  </langSet>
  <langSet xml:lang="fr-FR"> 
    <tig>
      <term>adresser</term>
      <termNote type="partOfSpeech">Verb</termNote>
    </tig>
  </langSet>
</termEntry>
```
Another crucial piece of information for the translator is the Part of Speech for the term. The standard provides a *partOfSpeech* attribute to the \<*termNote*> element at the \<*term*> level.

## Translating terms

In addition to finding the right translation for what the term means or does, there are other considerations. For example, should it be translated at all? Should it not even be included in the target? Should the translation include more or less than the source, due to peculiarities of the target audience?

### Translation vs. transliteration

Transliteration is the process of converting written script into another written script; for example, from English (Latin) to Russian (Cyrillic) or Japanese (Kanji). Transliteration is used primarily to make a term easier to read and pronounce in the target language. Transliteration doesn't address meaning; it focuses entirely on the characters that make up each word. When you're localizing your content, transliteration might come into play for names. For example, if you're translating from English to Russian or Chinese, you might transliterate the name so its pronunciation will come across to the reader. Within the Latin languages, some names have translated equivalents (for example, Guillermo for William). In these cases, the translator may choose to not translate the name. 

### Product names and key features: translate/transliterate/source

No rule governs the decision of whether to translate your product names. Some markets respond better to product names in their native language than others. Some don't. There are products that failed in target markets until they translated their product name, then succeeded after doing so. It's worth it to field-test the alternatives. You want your product names to be consistent across countries and you hope your markets will learn and value the product names. But above all you want foreign customers to buy the products. For feature names, you don't want the name to be an impediment to customer users. So feature names are more likely to be translated. As with people's names, since product names and key features might be new words, and therefore clumsy to translate, transliteration might be an alternative approach.  

### DNTs

In addition to product names and people's names that we've discussed above, there are many things you might not want translated. For example, brand names, trademarks, and key features might stay untranslated, to promote visibility and consistency across markets. Company names usually aren't translated, though there are exceptions. The titles of books usually aren't translated. College and university names usually aren't translated. Some languages have lexical gaps, where a word that exists in the source language doesn't exist in the target. There are many idioms that have no equivalents in some target languages. If your terminologist knows that a term has no translation in the target language, the term should be marked as a Do Not Translate (DNT). or the source should be reworked. 

### Acronyms and abbreviations

Acronyms can vary in different languages because they usually follow the order of the words they expand to. The abbreviations for single words can differ as well. For example, the abbreviation for the French word "premier" is "1\<sup>er\<\sup>". The Microsoft Style Guides for different languages often include a list of abbreviations that are different that language. See [Microsoft Language Portal](https://www.microsoft.com/Language/StyleGuides?rtc=1).

### Excluded terms (vulgarities, sensitive terms)

Your content might have words in it that are taboo or that are too sensitive to be seen by the target audience. This problem should be reflected in the annotation of the term entry. If possible, you should provide a translation that omits the vulgar or sensitive words while retaining the meaning of the source term.

### Slogans/tag lines

Your product tag lines and slogans have been carefully crafted, usually by the marketing department. As you create term entries for crafted phrases, you should work with the marketers that created the originals, to get their approval for the translations. This approval should be indicated with an annotation for the term entry. [Willie: Anything else about "phrases" (Your original heading was "Phrases/tag lines)?]
