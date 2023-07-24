---
title: Localize documentation
description: Localizing documentation and user assistance involves adapting and translating your existing content. Recycling existing translation involves additional challenges.
author: m-kauppinen
ms.author: v-mikau
ms.topic: conceptual #Required; leave this attribute/value as-is.
ms.date: 07/12/2023

---

# Localize documentation

Documentation for a product can include printed or PDF manuals, online support pages, and context-sensitive help. Documentation (or content) localization has some major differences when compared to software localization.  Having more text means that the localization will take longer and cost more. Thus keeping localized content (or software, for that matter) in sync with the source content can be challenging. Revisions made after the first complete translation can also be costlier than you would think at first: changing one word in a sentence might mean the whole sentence needs to be reworked to sound natural. It is important to keep track of changes to avoid unnecessary localization costs. Computer-aided translation (CAT) tools such as [translation memories (TM)](translation-memories.md) can greatly help this.

Structured authoring and documentation can reduce localization costs. At a bare minimum, this means using styles in a Word document instead of formatting everything manually . A better solution involves using structured markup language, such as [Markdown](https://www.markdownguide.org/) or [DITA XML](https://www.xml.com/articles/2017/01/19/what-dita/).

For software localization, a segment is typically a string. In-context matching is typically achieved by a combination of filename, string id, and string text. For documentation, a segment can be a block-level element such as a paragraph or a list item, but can also be a sentence within a block-level element. In-context matching can be achieved by comparing the segment before and after the segment to be translated, as well as the segment’s text.

Content localization tends to be done after UI localization, so translations of UI terms should be available to make the work easier. However, you should consider your product’s content localization schedule carefully. User documentation is often finished shortly before the product is shipped, because it needs to be as up-to-date as possible. The large volume of text along with a later delivery schedule means a tight localization schedule.

## Technical considerations

Here are a few examples of things you need to consider when localizing documentation. They are meant to illustrate that the simplest, smallest things you might not even think about can work differently in localized text.

Indexing has different sorting conventions from language to language. Your localized documentation should follow the rules of the target language to ensure a positive user experience. For more information and examples about sorting text strings in various languages, refer to [Collation, sorting, and string comparison](../locale/sorting-and-string-comparison.md).

Line and word breaks  work differently in some languages that do not use the Latin script. For example, in English it is simple to automatically break a line at a space or hyphen. But languages such as Chinese, Japanese, Korean, and Thai have different guidelines which the localized version needs to follow. Thai does not use spaces between words, but line breaks must still be placed at word boundaries. In Japanese you can break a line between any two characters – but there are exceptions to the rule.

If your documentation is going to be printed, you might need to redo the layout for the localized version, depending on your target market. Most of the world uses the standardized paper sizes defined in ISO 216:2007, which include the popular A4 size, for example. The US and a few other countries use the American inch-based paper sizes such as Letter and Legal.
