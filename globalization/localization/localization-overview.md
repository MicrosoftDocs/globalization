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

Localization of a product requires that the product is adapted to both the language and the culture of a particular market. A major step in this process is to identify what does and what doesn't need to be translated. Certainly the software and documentation needs to be translated. However, there's more to consider: Marketing material, websites, videos, customer support content, sample data, even chatbots! These other deliverables are all part of the customer's engagement with the product.

## Isolating the materials to be translated

You need to isolate the materials you've identified as needing to be translated. All of your deliverables—software, documentation, marketing materials, videos (the dubbing, subtitling, recreation), websites, and sample data—have components that are translatable. This translatable material might need to be extracted and, after translation, reinserted into the deliverable.

## Correct sequencing of materials to be translated

You should consider the order in which you provide materials to the translators. For example, you wouldn't want translators to start translating the documentation of the features in the product before strings for the features have been translated. Translating the software first allows you to build and approve translation memories and terminology lists to be used for the documentation.

## Identifying translation resources

You should identify who is going to do the translating. Will it be a Language Service Provider (LSP)? A single-language vendor (SLV), a multi-language vendor (MLV), or a freelancer? With freelancers, there's less overhead but the management burden falls upon you. MLVs might have more fixed costs than SLVs, but a single point of contact has advantages if your project requires multiple target languages. You should investigate the advantages and disadvantages of each of these alternatives for the scope and type of your project. You should also validate that they have the skills and domain knowledge for your project.

Typically, a translation project will include the following personnel:

- project managers who receive and return the files
- project engineers who prepare the material for the translators, so that the translators receive only text to translate
- linguists to monitor linguistic issues
- the translators themselves

You should ensure that all of these tasks are covered by the agency or freelancers you select.

## Preparing and delivering materials to translation resources

You should provide localization vendors more than just the strings, multi-media files, and image files that need to be translated and localized. It's very much in your interest to provide them reference materials like style guides, translation memories, and terminology lists. You should establish the expected format for interchange the data. They should have access to the English (or source language) software and product documentation for reference. They should know the purpose, context, and scope of the project, along with the expected criteria for your satisfaction in the quality of the translation. LSPs should receive a schedule upon which to base their own schedule, and test plans for validating success. These test plans are tied to the criteria for success and can serve as the plan followed for QA testing. Therefore, if a different vendor handles the QA, the LSP that handles the translation itself should also receive the test plans. For screenshots, you should provide steps for recreating the screenshot.

### Style Guides

Each target market has different style considerations. Style guides convey, for example, the tone and level of formality you should aim for when addressing the user. You should obtain and adhere to a style guide for the language of target market early in your product design cycle. Microsoft has full style guides for all languages at [Microsoft Language Portal](https://www.microsoft.com/en-us/Language/StyleGuides?rtc=1). These style guides contain sections on localization, and general style issues for the language. For example, many of the style guides have sections on abbreviations, idioms, and colloquialisms, in addition to spelling, punctuation, grammar, and capitalization conventions. For smaller projects, style guides covering the top 10 most important rules from the full style guides can be found at [Quick Start localization style guides](https://docs.microsoft.com/en-us/globalization/localization/styleguides).

In addition to the software or documentation material that you deliver to the party managing and doing the translation. you 

### XLIFF

The material you send to the party doing the translation might be in various formats. For software, you might send RESX, INI, or properties files, among many other formats. For your documentation, you might send Office, InDesign, FrameMaker, HTML, or Trados TTX files, among other formats. To accommodate this variety of formats, translation operations need an interchange file format.

XML Localization Interchange File Format (XLIFF) is a bitext XML format for exchanging localizable data. A bitext is a document that includes both source and target language versions of a given text. The bitext format includes the pairing of the source and target language strings of each segment in the document. It gives you a single file format for translating different kinds of documents. XLIFF filters isolate text from the document type layout. XLIFF is commonly used by CAT tools to exchange data. CAT tools that use XLIFF have filters for common source file formats: HTML, XML and other markup languages, RTF, Microsoft Office products, InDesign, FrameMaker, plain text, and more. These filters store the non-translatable material in what are called skeletons. The skeleton files are used for reassembling the translated material into the original format for previewing the translations and for final delivery.

The latest version, XLIFF 2.0, is defined by ISO 21720. You can obtain the ISO 21720 XLIFF standard [here](https://www.iso.org/obp/ui/#iso:std:iso:21720).

#### The XLIFF format

An XLIFF file contains tags for source and target segment pairs, within a translation unit element. A translation unit may be a single word, a phrase, one or more sentences, or even a larger unit. The larger the translation unit, the more meaningful, or idiomatic, the translation will tend to be. However, there are problems with making a translation unit too long. With longer units, there's less chance of finding a complete match for the source segment. Furthermore, if the translation unit is so long that there are few units in the document, a minor change would be harder to detect.

Each translation unit tag has an ID. There are tags for source language and target language, and original file ID and name. The other important tag identifies the skeleton file (a `.skl` file). Here's a simple example of an XLIFF file with two translation units:

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

### Translation memories

A translation memory (TM) is a database of previously translated source and target language pairs called translation units (which we also see in XLIFF). TMs are used by Computer-Assisted-Translation (CAT) tools to suggest translations for a given source segment. Segments are typically sentences, but can be paragraphs, headings, list items, or whatever is determined by the segmentation rules of the CAT tool. When the translator connects to a TM, the tool offers the best match it finds for each segment.

TMs can be used to analyze how much work the translator faces. Most CAT tools have a word counting program that analyzes the document. The translations offered are marked by what kind of match they are. They could be in-context matches, 100% matches, fuzzy (that is, partial) matches, repetitions, or no match found. The analysis reports the number of words in each category. This report can be used to estimate the cost of the translation.

As translators work in the CAT tool, they can save their translations to the TM. A project can start with an empty TM, and when it's done, you'll have a TM that can be used for subsequent projects.

Translation memories are essential for maintaining your product. Especially if you release your product simultaneously in multiple languages, the translation work will typically begin while product development is still underway. Reusing previous translations as you update the product greatly accelerates the translation process. Since most software products are updated periodically by adding features to a base product, reapplying your existing translation work makes the translation work incremental.

TMs have a standard XML interchange format, called Translation Memory eXchange (TMX). See [here](https://www.gala-global.org/tmx-14b).

#### Translation memory maintenance

The most common and continual updating of the translation memory is done by the translators when they save their translations to the TM while working on the project documents. But there's always some mending and amending to do: You might want to perform global terminological changes to all translations stored in the memory. Or you might need to update the memory with files that have been translated for another project using another TM. Your linguistic assets require dedicated maintenance. Some CAT tools provide editors for maintaining TMs and terminology lists.

A good practice is to have a primary TM, to which only approved translation units are saved. Translators can connect to a copy of the primary TM for their working TM. But the working TM translations shouldn't be merged into the primary TM until every translation unit has been reviewed and approved. 

A TM file stores translation and linguistic data in a structured format, typically in Extensible Markup Language (XML). The most common TM format is Translation Memory eXchange (TMX). TMX is the primary format for exchanging TM data between CAT tools. A large company will likely have a library of TMs, spread across technologies. This standard format makes it easier to import, export, and maintain consistency across TMs.

### Terminology

Your product no doubt contains many terms that are specific to it, and whose translation you should control carefully. You use terminology lists (also called term bases or glossaries) for these terms. Some of these terms you want translated in a specific way; some you don't want translated at all. For example, product names are often not translated. Company names are almost never translated. Your terminology lists should be developed by internal teams (marketing, software, documentation, and linguistic engineers) and external (LSP) teams. Like translation memories, they need to be curated. Terminology lists can be linked to TMs, giving all translators access to the same resources and reference material. 

Like TMs, terminology lists have a standard XML interchange format, called TermBase eXchange (TBX). You can obtain the ISO 30042 TermBase eXchange (TBX) standard [here](https://www.iso.org/standard/62510.html/). See [Managing terminology](managing-terminology.md).

### Linguistic validation

Part of the maintenance of your linguistic assets is to ensure that each translation is linguistically accurate, culturally appropriate, and validated by an expert. Such linguistic validation is important in all fields, but is crucial for things like the translation of clinical trials, scientific instructions, and legal documents. In these areas, there are regulatory processes for ensuring linguistic accuracy.

To ensure your TMs and terminology lists are correct, they should be reviewed by linguists, in-country marketing personnel, and subject matter experts. For specialized fields like life sciences and legal services, linguistic validation can be a rigorous process. The validation could require reconciliation of back translation with the original translation, plus professional review. See [Linguistic validation](https://docs.microsoft.com/en-us/globalization/testing/linguistic-validation).

## Receiving translated materials and generating deliverables

When you have received translated materials from the localization vendor, you need to incorporate them into your product delivery. This process requires planning. For software translations, do you need to recompile the system? For web content, do you have a location prepared for where the translated files are to be placed, so they can be linked to by a language selector? For help systems, do you have a link to a location set up for them in the product? If the files are to be stored in a content management system (CMS), is their storage location prepared? Are there reusable chunks of content? If so, are the links to these chunks in place? Are there image files whose links need to be validated?

Another major consideration is maintenance of the TMs and terminology lists that the vendor returns to you. These linguistic assets will be the basis for cost-saving and quality in future projects. You want to have established a process for curating them and for storing them in a logical way, so they can be easily located for future projects. Since your company terminology and your product features themselves are likely to change, going forward, it's a good idea to have these linguistic assets updated accordingly as the products evolve. 

## Review and validation

Before translated files are restored to their original file format and delivered to the customer, they must be reviewed and validated. For software translation, you need the translations inserted into the original deliverable and to review the running application. For content translation, the reviewer uses the same presentation medium that users see. ICR isn't the same as the linguistic validation performed during linguistic asset maintenance. More problems can be observed when the linguistic validation is performed in the context of the user's experience, rather than at the resource level. So the team responsible for the linguistic asset curating should collaborate with the team performing in-context review. See [In-context review (ICR)](https://docs.microsoft.com/en-us/globalization/testing/in-context-review).

## Next steps
<!-- Add a context sentence for the following links -->
- [Managing terminology](managing-terminology.md)
- [Maintaining a translation memory](translation-memories.md)
- [Localize software](localize-software.md)
- [Content localization](localize-content.md)
- [Localize games](localize-games.md)
- [Video and multimedia localization](video-multimedia.md)
- [Transcreation localization strategy](transcreation.md)