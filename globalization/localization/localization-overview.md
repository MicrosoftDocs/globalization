---
title: Localize your product
description: Understand the process of localization and strategies for localizing different types of content. (localize/l10n)
author: m-kauppinen
ms.author: v-mikau
ms.topic: conceptual #Required; leave this attribute/value as-is.
ms.date: 07/14/2023

---

# Localizing your product

Whether your deliverables include [software](localize-software.md), [games](localize-games.md), [multimedia](../media/video-multimedia.md), [documentation](localize-content.md), or websites, they need to be localized for the target audience if you want to increase customer satisfaction and give your product access to new markets, meaning new sources of revenue.

Localization is not the same thing as translation, even though people often use the words interchangeably. Translation is an important part of localization, but not the only one. Translation changes the text of your deliverable into another language. In some cases, that might be enough, but usually you need to adapt more than just the textual content for your target audience. For example, a sentence in US English that mentions the cost of a train ticket on a given date needs to be adapted when localizing it for, say, German or Egyptian audiences. The cost should use the local currency (unless there is a reason to keep it in US dollars) and the date format needs to be changed from month-day-year to the local format, such as day-month-year. Sometimes localization doesn’t even involve translation into another language, for example, when localizing a product from US English to UK English.

The above example is greatly simplified. Localization affects your entire deliverable, not just its textual content. To make localization as smooth as possible, you should design your product to be adaptable to different audiences with as few engineering changes or rework as possible. This advance planning and preparation is known as internationalization.

When localization and internationalization are done correctly, the following things and more are considered:

- Cultural differences such as cultural references, idioms, symbolic meanings, taboos; for example, ground floor vs. first floor, or football vs. soccer
- Different calendars, date, time, and currency formats
- Metric vs. imperial measurements
- Text length: text translated from English into many other languages can be considerably longer, which might create layout issues
- Orthography, including punctuation and capitalization
- Direction of writing: languages such as Arabic and Hebrew are written from right to left
- Different keyboard layouts
- Legal requirements such as compliance with Europe’s General Data Protection Regulation (GDPR)
- Visual elements such as images, videos, icons, and UI elements

## Identifying the materials to be translated

A major early step in the localization process is to identify what needs to be translated in your project. This starts with all text visible to users in your deliverables and its accompanying documentation. But you need to consider more than that. Images, videos, marketing material, websites, customer support content such as FAQs, sample data, even chatbots. These other deliverables are all part of the customer's engagement with the product. With multimedia, you need to weigh the costs and benefits of [re-creation and dubbing](../media/re-creation.md) against [captioning and subtitling](../media/captioning.md). With critical content like marketing material, you might want to do a full [transcreation](transcreation.md).

## Ensuring that materials to be translated are correct

It is important to verify that the source materials are ready for translation. This could include validating that all terminology is being used correctly and consistently, and that grammatical and orthographical errors have been fixed. These types of errors can significantly slow down the translation process, and they typically introduce additional localization cost as retranslation is required after source text changes. You should aim to have all your terminology approved and frozen before going into translation.

## Isolating the materials to be translated

You need to isolate the materials you've identified as needing to be translated. All your deliverables—[software](localize-software.md), [documentation](localize-content.md), [marketing materials](transcreation.md), videos (dubbing, [subtitling](../media/captioning.md), even [re-creation](../media/re-creation.md)), websites, and sample data—have components that are translatable. This translatable content usually needs to be extracted from the source files so that translators can focus solely on the textual content. Any non-translatable content should be the responsibility of [engineers and desktop publishers](#identifying-translation-vendors). After translation the textual content is then reinserted into the source files. In some cases your translation vendor can perform the extraction for you.

This approach also lets you use the same source materials to support multiple languages. The source might need some modification to make this possible, but this is still much better than having separate software binaries for each language, or creating a new layout from scratch for every localized version of your documentation or marketing materials. The separation of translatable content from code is discussed under "Separating your code from your translatable strings" in [Localize software](localize-software.md).

## Sequencing of materials to be translated

You should consider the order in which you want the materials to be translated. For example, it might be preferable to not translate the user documentation before the UI strings for the features have been translated. Translating the software first allows you to build and approve translation memories and terminology lists, which are then used when translating the documentation. If your deliverables include a glossary or a similar document, that should also be prioritized for the same reason. For more information, refer to [Manage terminology](managing-terminology.md).

This approach is not the only possible one, however. Sometimes translators find that reading and translating the documentation leads them to rethink some UI terminology translations from a more informed viewpoint. Thus you should consider the sequencing separately for each new project.

## Identifying translation vendors

There are various ways to handle a translation project. Will you contact a Language Service Provider (LSP), single-language vendor (SLV), a multi-language vendor (MLV), or a freelancer? With freelancers, there's less overhead but the management burden falls upon you. MLVs might have more fixed costs than SLVs, but a single point of contact has advantages if your project requires multiple target languages. You should investigate the advantages and disadvantages of each of these alternatives for the scope and type of your project. You should also validate that they have the skills and domain knowledge for your project.

A translation project could involve the following roles:

- Project managers who schedule and monitor the project and communicate with all other roles
- Engineers who prepare the material for the translators, so that the translators receive only the translatable materials in the right format
- Linguists who monitor linguistic issues and manage style and terminology
- Desktop publishers who handle layout-related tasks
- Testing/quality assurance resources who verify the quality of the localized deliverables
- Translators

Your organization might have some of these capabilities available internally. When planning your localization project, you should ensure that all these tasks are handled either in-house or by the agency or freelancers you select.

## Preparing and delivering materials to translation vendors

You should provide the localization vendor more than just the strings, multimedia files, and any other materials that need to be translated and localized. Sharing any reference material you have helps to ensure the quality of the localized product. This includes style guides, [translation memories](translation-memories.md) (TMs), and [terminology lists](managing-terminology.md). If the vendor is responsible for recreating screenshots in the languages of the translated deliverables, you should provide steps for recreating the screenshot, so that matching screenshots can be taken when the translated UI is available.

You should also establish the expected format for interchanging the data (such as the widely used [XLIFF format](localization-file-formats.md)). The vendor should have access to the English (or other source language) software and product documentation for reference. They should know the purpose, context, and scope of the project, along with the expected translation quality criteria.

Finally, LSPs need a schedule on which to base their own schedule and test plans for validating success. If you are using different vendors for translation and QA, only the vendor responsible for the QA needs the test plans.

The materials you need to send to the vendor are discussed in more detail below.

### Source material in an interchangeable format

The material you need translated is often in various formats. Your software strings might be isolated in any number of file formats including .resx or Java .properties files. Your documentation and marketing material might be created using Office, InDesign, FrameMaker, or HTML, to name a few. To accommodate this variety of formats, translations can use an interchangeable data format into which all kinds of source formats can be parsed. XML Localization Interchange File Format (XLIFF) is one such format that is commonly used. For more information, refer to [Localization file formats](localization-file-formats.md) and [Exchanging localizable resources](exchanging-localizable-resources.md).

You should agree with your translation vendor who will handle the extraction of translatable content from the various source files. If you send the source files to the vendor as is, it is simpler for you, but likely more costly since they will in most cases need to perform the extraction before sending out the translatable text to the translators. The other option is to perform the extraction of the translatable content yourself and send it to the vendor in an interchange format.

### Style guides

Style guides convey, for example, the tone you should use when addressing the users, typographic conventions for things like headings, tables, and code snippets, grammar and punctuation rules, and more. You should establish a style guide early in your product design cycle and thereafter follow it to ensure that the source material is consistent before any translation project starts. Different markets have different style considerations, so you should also have style guides for each target language. This lets you maintain a unified “company feel” while addressing users in different cultures in the way they are accustomed to.

### Existing translation memories

A [translation memory](translation-memories.md) (TM) is a database used and updated by translators as well as localization teams in your organization. It consists of previously translated source and target language pairs called translation units. TMs are essential for maintaining your product across product updates and target languages. Reusing existing translations increases consistency and will also save costs. A large company will likely have a library of TMs for different purposes.

TMs have a standard XML interchange format, called Translation Memory eXchange (TMX). This standard format makes it easier to import, export, and maintain consistency across TMs.  For more information, refer to [Localization file formats](localization-file-formats.md).

### Existing terminology

When you use terms that have specific meanings within your products, you should also manage the translation of these terms carefully. You use terminology lists (also called termbases or glossaries) to manage these terms. Some of them you might want translated in a specific way, while some you don't want translated at all. For example, product names are often not translated, while names of features might be translated.

Your terminology lists should be developed by both internal teams such as marketing, software, documentation, and linguists, as well as external (LSP) teams. Like TMs, they need to be kept up to date when terms evolve or become obsolete. Terminology lists can be linked to TMs, giving all translators access to the same resources and reference material. Like TMs, terminology lists have a standard XML interchange format, called TermBase eXchange (TBX). For more information, refer to [Manage terminology](managing-terminology.md).

## Linguistic validation

Part of the maintenance of your linguistic assets is to ensure that each translation is linguistically accurate, culturally appropriate, and validated by an expert. Such linguistic validation is important in all fields, but it is crucial for things like the translation of clinical trials, scientific instructions, and legal documents. In these areas, there are regulatory processes for ensuring linguistic accuracy. Examples include [ISO 13485:2016](https://www.iso.org/standard/59752.html) that covers medical devices and [ISO/IEC 17025:2017](https://www.iso.org/standard/66912.html) that covers requirements for testing and calibration laboratories.

To ensure your TMs and terminology lists are correct, they should be reviewed by linguists, in-country marketing personnel, and subject matter experts. For specialized fields like life sciences and legal services, linguistic validation can be a rigorous process. The validation could require reconciliation of back translation with the original translation, accompanied by a professional review.

## Receiving translated materials and generating deliverables

When you have received translated materials from your vendor, you need to incorporate them into your product delivery. This process requires planning. Here are some examples of things you need to consider:

- For software translations, how will you build your product to include the translated resources?
- For web content, do you have a content management system that can handle your translated resources?
- For help systems, is your product able to link to the content in the appropriate language?
- If the files are to be stored in a content management system (CMS), does it support the locales that you need?

Another major consideration is maintenance of the TMs and terminology lists that the vendor returns to you, as discussed in [Translation memories](translation-memories.md) and [Manage terminology](managing-terminology.md). These linguistic assets will help to save costs and ensure quality in future projects. You should have an established process for curating them and storing them in a logical way, so they can be easily reused for future projects.

## Review and validation

Before the localized content is ready for integration into your product and distribution to the target market, it must be reviewed and validated. For software translation, you need the translations inserted into your product so that the running application can be reviewed. For content translation, the reviewer uses the same presentation format that the users will see. This process isn't the same as the linguistic validation performed during linguistic asset maintenance. “Linguistic correctness” (grammar, spelling, following the style guide, and so on) is what linguistic validation aims for, but unless the reviewer can see the content in the actual user context, it might be difficult to confirm the appropriateness of the translation. The team responsible for the linguistic asset curating should collaborate with the team performing an in-context review.
