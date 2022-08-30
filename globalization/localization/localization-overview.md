---
title: Localization Overview - How localization works
description: This article helps you understand the process of localization and strategies for localizing different types of content.
author: v-williamsw
ms.author: v-williamsw
ms.topic: overview
ms.date: 01/01/2022
ms.custom: template-overview
---

# Localizing your product

Internationalization is the process of designing and creating a product with globalization and localization considerations as part of the design. When you design your product to be localized, there are similar concerns, whether you're designing software, content, multi-media, or marketing material.

## Identifying the materials to be translated

Localization of a product requires that the product is adapted to both the language and the culture of a particular market. A major step in this process is to identify what does and what doesn't need to be translated. Not all your material should be translated. For software, you obviously don't want your executable code translated, since the compiler is expecting a programming language, not a human language. However, your code contains elements that you do want translated. Among these elements requiring localization are:

- Menus
- Notifications and error messages
- Dialog boxes
- Prompts
- Tooltips
- Images
- Sounds
- Toolbars
- Status bars
- Constants

You don't want to leave the decision of what to translate in your product up to the translator. The translator isn't expected to know what is executable code and what is an element that should be translated. The translator could easily break your code by removing or altering a program character. Best to send the translator only what needs to be translated. Some of what you do send to the translator can be marked as "Do not translate" in the translation memories or terminology lists.

For your product content, the identification of what should and should't be translated can be controlled by the translation memories or terminology lists (also called glossaries) that offer translations. For segments and terms that shouldn't be translated, only the original language will be offered.

## Isolating the materials to be translated

You need to isolate the materials you've identified as needing to be translated. For software, we recommend that you put everything that needs to be translated into a resource repository. You could put this material into Windows resource files, .NET assembly files, or, for Web content, a database. See [Localize software](localize-software.md).

For your content, you'll send the documents that need to be translated to the translation team, along with translation memories and terminology lists. Engineers on the translation team will apply filters to this formatted material to strip out non-translatable elements, so the translators will be able to translate only the material that should be translated. See [Localize content](localize-content.md).

For games....[Willie: Add a paragraph for games.] See [Localize games](localize-games.md).

## Correct sequencing of materials to be translated

You should consider the order in which you provide materials to the translators. For example, you wouldn't want translators to start translating the documentation of the features in the product before the user interface and command line strings that need translating have been translated. Also, translating the software first allows you to build and approve translation memories and terminology lists to be used for the documentation. [Willie: Are there other sequencing issues?]

## Identifying translation resources

You should identify who is going to do the translating. Will it be a Language Service Provider (LSP)? A single-language vendor (SLV), a multi-language vendor (MLV), or a freelancer? You should investigate the advantages and disadvantages of each of these for the scope and type of your project. You should also validate that they have the skills for your project.

Typically, a translation project will include the following personnel:

- project managers who receive and return the files
- project engineers who prepare the material for the translators, so that the translators receive only text to translate
- linguists to monitor linguistic issues
- the translators themselves

Sometimes one person does more than one of these tasks.

## Preparing and delivering materials to translation resources

You should provide LSPs more than just the strings, multi-media files, and image files that need to be translated and localized. It's very much in your interest to provide them, as well, translation memories, terminology lists, style guides, and fonts. They should have access to the English (or whatever the source language is) software and product documentation, for reference. They should know the purpose, context, and scope of the project, along with the expected criteria for your satisfaction in the quality of the translation. LSPs should receive a schedule upon which to base their own schedule, and test plans for validating success. For screenshots, you should provide steps for recreating the screenshot.

For content translation, instead of providing strings you've extracted from a repository, you might provide the entire document (or help system source) that is to be translated. Project engineers for the LSP will likely pre-process files such that they can be loaded by the translator into a Computer-Aided-Translation (CAT) tool. This pre-processing often involves converting the files into industry standard XLIFF files, in which the content is divided into segments that can be thought of as translation units. In this case, the project engineers will deliver files in the format the CAT tool can use to present strings to the translator.  

### XLIFF

XML Localization Interchange File Format (XLIFF) is a bitext XML format for exchanging localizable data. The bitext format includes both the source and target language strings of each segment in the document. The segments are generated by a tool that aligns the beginning and end of the target strings with those of the source strings. XLIFF is commonly used by CAT tools to exchange data. It gives you a single file format for translating different kinds of documents. XLIFF filters isolate text from the document type layout. CAT tools that use XLIFF usually have filters for the most common formats: HTML, XML and other markup languages, RTF, Microsoft Office products, InDesign, FrameMaker, plain text, and more. These filters store the non-translatable material in what are called skeletons. The skeleton files are used for reassembling the translated material into the original format for previewing the translations and for final delivery.

#### ISO 21720

XLIFF 2.0, as stated in the ISO standard itself, consists of "the minimum set of XML elements and attributes required to (a) prepare a document that contains text extracted from one or more files for localization, (b) allow it to be completed with the translation of the extracted text, and (c) allow the generation of Translated versions of the original document." You can obtain the ISO 21720 XLIFF standard [here](https://www.iso.org/obp/ui/#iso:std:iso:21720).

#### The XLIFF format

An XLIFF file contains tags for source and target segments, within a translation unit element. Each translation unit tag has an ID. There are tags for source language and target language, and original file ID and name. The other important tag identifies the skeleton file (a `.skl` file). Here's a simple example of an XLIFF file with two translation units:

    <xliff xmlns="urn:oasis:names:tc:xliff:document:2.0" version="2.0" srcLang="en-US" trgLang="fr-FR">
    <file id="f1" original="Simple_Example.html">
          <skeleton href="Simple_Example.html.skl"/>
          <unit id="1">
              <segment>
                  <source>Hello world</source>
                  <target>Bonjour le monde</target>
              </segment>
           </unit>
           <unit id="2">
               <segment>
                   <source>This is an XLIFF document.</source>
                   <target>Il s'agit d'un document XLIFF.</target>
               </segment>
            </unit>
    </file>
    </xliff>


## Translation memories

A translation memory (TM) is a database of previously translated source and target language pairs called translation units. TMs are used by Computer-Assisted-Translation (CAT) tools to look up and fetch suggested translations for a given source segment. Segments are typically sentences, but can be paragraphs, headings, list items, or whatever is determined by the segmentation rules of the CAT tool. Segmentation rules are configurable. The CAT tool segments the document to be translated, then looks up each segment in one or more TMs and offers translations. 

In addition to loading translations into the document, TMs can be used to analyze how much work the translator faces. The translations offered are marked by whether they're in-context matches, 100% matches (but not in-context), fuzzy matches (for example, where, say, 75% of the words in the segment are matched), repetitions, or no match found. This analysis can be used to estimate the cost of the translation.

As translators work in the CAT tool, they can save their translations to the TM. Some CAT tools serve the TMs from the cloud, such that a TM unit saved by one translator becomes available to other translators that are connected to that TM. Furthermore, TMs can be connected to other TMs. A translator typically connects directly to a working TM, to which the translator can save translations. This working TM can in turn be connected to read-only "background" TMs. The background TM matches can be assigned premiums or penalties that are computed into the match percentage when matches from them are offered to translators. More than one translation can be offered for a given source segment. When multiple matches are found among the TMs, the one with the highest match percentage is offered first.

More recently, some CAT tools support machine translation (MT) TMs. Even with the dramatic advances in machine translation, the quality of machine translation results isn't at the same level as high-level manual translation. Therefore translations offered from MT TMs are marked as such.

## Terminology

Your product no doubt contains many terms that are specific to it, and whose translation you should control carefully. You use terminology lists (also called term bases or glossaries) for these terms. Some of these terms you want translated in a specific way; some you don't want translated at all. Your terminology lists should be curated by your linguistic engineers. Terminology lists can be linked to TMs, giving all translators access to the same resources and reference material.

## Style Guides

Each target market has different style considerations. Style guides convey, for example, the tone and level of formality you should aim for when addressing the user. They contain information on market-specific data formats. You should obtain and adhere to a style guide for the target market early in your product design cycle. Microsoft has full style guides for all languages at [Microsoft Language Portal](https://www.microsoft.com/en-us/Language/StyleGuides?rtc=1). For smaller projects, style guides covering the top 10 most important rules from the full style guides can be found at [Quick Start localization style guides](https://docs.microsoft.com/en-us/globalization/localization/styleguides). 

## Translation and TM maintenance/reuse

Translation memories are essential for maintaining your product. Especially if you release your product simultaneously in multiple languages, the translation work will have to begin while product development is still underway. Reusing previous translations as you update the product greatly accelerates the translation process. Since most software products are updated periodically by adding features to a base product, reapplying your existing translation work makes your work incremental.

The most common and continual updating of the translation memory is done by the translators when they save their translations to the TM while working on the project documents. But apart from that, there's always some mending and amending to do: You might want to perform global terminological changes to all translations stored in the memory. Or you might need to update the memory with files that have been translated for another project using another TM. Your linguistic assets require dedicated maintenance. Some CAT tools provide editors for maintaining TMs and terminology lists.

A translation memory file stores translation and linguistic data in a structured format, typically in Extensible Markup Language (XML). The most common TM format is Translation Memory eXchange (TMX). TMX is the primary format for exchanging TM data between CAT tools. A large company will likely have a library of TMs, spread across technologies. This standard format makes it easier to import, export, and maintain consistency across TMs.

### Linguistic validation

Part of the maintenance of your linguistic assets is to ensure that each translation is linguistically accurate, culturally appropriate, and validated by an expert. Such linguistic validation is important in all fields, but is crucial for things like the translation of clinical trials, scientific instructions, and legal documents. In these areas, there are regulatory processes for ensuring linguistic accuracy. See [Linguistic validation](https://docs.microsoft.com/en-us/globalization/testing/linguistic-validation).

## Receiving translated materials and generating deliverables

For software translation, if you've followed the recommendation of putting your translatable strings into a resource repository, the party doing the translation, at a minimum, should receive those strings to translate. It's the product developer's responsibility to ensure that the user interface accommodates the translated strings. The translated strings can take up as much as 30% more space than the source strings in some languages. You should therefore provide a user interface with expanded controls and buttons in the dialog boxes for those languages. If the software was developed using Unicode, the party doing the translation shouldn't need to worry about character encoding issues.

For content translation, typical steps (and step owners) for the responsible party are:

1. Reception of the content files from customer (project manager)
2. File, TM, Glossary, and filters preparation (project engineer and linguist) to present the translator with strings/segments to translate
3. Translation (In-country translator)
4. Restoration of file format (project engineer)
5. Delivery of files to customer (project manager) 

The steps would be different for software and games translation.
[Willie: explain these steps more fully.]

## Review and validation

Before translated files are restored to their original file format and delivered to the customer, they must be reviewed and validated with an in-context review (ICR). For software translation, ICR is linguistic validation of the running application. For content translation, the reviewer uses the same presentation medium that users see. ICR isn't the same as the linguistic validation performed during linguistic asset maintenance. More problems can be observed when the linguistic validation is performed in the context of the user's experience, rather than at the resource level. See [In-context review (ICR)](https://docs.microsoft.com/en-us/globalization/testing/in-context-review).

## Next steps
<!-- Add a context sentence for the following links -->
- [Managing terminiology](managing-terminology.md)
- [Maintaining a translation memory](translation-memories.md)
- [Localize software](localize-software.md)
- [Content localization](localize-content.md)
- [Localize games](localize-games.md)
- [Video and multimedia localization](video-multimedia.md)
- [Transcreation localization strategy](transcreation.md)