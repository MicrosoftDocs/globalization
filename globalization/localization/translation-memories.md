---
title: Maintain translation memories
description: A translation memory (TM) represents a significant asset that demands careful maintenance.
author: m-kauppinen
ms.author: v-mikau
ms.topic: conceptual #Required; leave this attribute/value as-is.
ms.date: 07/12/2023

--- 

# Maintain translation memories

Computer-aided translation (CAT) is a process where translators are assisted by various software tools when translating text from one language into another. CAT tools can include Translation Memory (TM) tools, terminology tools, spelling and grammar checkers, and machine translation tools. Translation memories are databases that contain text segments in a source language that are paired with translated segments in one or more target languages. Each segment could be a word, a sentence, or an entire paragraph.

If you are a translator who works using a TM, you can benefit from your previous work or work that other translators have done in the past. Every time you start a new project for a customer you have previously worked with, the corresponding TM might contain translations that can be reused in the new project. Every project translators work on with the TM adds to the information stored, making it more comprehensive and more likely to find matches.

During the translation process, these tools can automatically segment the source text according to a set of rules which can be defined for each project. Segmentation happens after translatable strings are extracted from the source files, separating them from the code or other non-translatable content. Extraction and segmentation are usually done by an engineer when the source files arrive from the client. For more information about the phases of the localization process, refer to [Localizing your product](localization-overview.md).

## Key formats and standards

As mentioned above, there are different kinds of CAT tools. Since these tools are made by various companies and some of them use proprietary file formats, there is a clear need for standardized formats to make data exchange between tools possible. The three most common formats are described below.

Translation Memory eXchange (TMX) is an XML specification for exchanging translation memory (TM) data. TMX used to be owned by Localization Industry Standards Association (LISA), but since 2011, the standards have been posted under a Creative Commons Attribution 3.0 License. The current version of TMX is the [TMX 1.4b Specification](https://www.gala-global.org/tmx-14b) from 2005.

TermBase eXchange (TBX) is a standard ([ISO 30042:2019](https://www.iso.org/standard/62510.html) and the functionally identical [LISA TBX document](https://www.gala-global.org/sites/default/files/migrated-pages/docs/tbx_oscar_0.pdf)) that defines an XML format for exchanging terminology data. It was also originally released by LISA. Today it is available as an open standard and as an ISO standard.

XML Localization Interchange File Format (XLIFF) is an XML-based format for standardizing how localizable data is passed between tools during localization. It is a common format for CAT tool exchange. XLIFF is an Organization for the Advancement of Structured Information Standards (OASIS) standard. [XLIFF Version 2.1](http://docs.oasis-open.org/xliff/xliff-core/v2.1/xliff-core-v2.1.html) is the current version.

## Importing data to a TM

A translator doesn’t necessarily need to rely only on their own past work to develop their TM. They might have access to one or more TMs from previous translation work done for the client. TMs can be merged by using the TMX data format even if their native formats are different. Merging TMs should be done carefully, however, or translators might run into issues described in [Maintaining translation memories](#maintaining-translation-memories).

## Translating with a TM

Translators usually start a new assignment after an engineer has processed the source files as described in the introduction. The translators might be using a web-based CAT tool where the translatable strings have been uploaded for them, or a local tool, in which case the strings are delivered to them as one or more files. These files are either in the tool’s proprietary format or a standardized one, such as XLIFF. The translators also need access to a TM and terminology. Both of these can also be available via the web-based CAT tool, or delivered as files in the TMX and TBX formats, respectively.

During the engineering phase, the translatable text has been divided into segments, which are compared to the data stored in the TM so that any matching segments can be retrieved. The matching segments can be perfect matches, where the source text is a 100% match to a previously stored segment. However, there are two kinds of 100% matches:

- Only the segment itself (in this case usually a sentence) is identical to a previously translated sentence.
- The segment and the segments before and after it are a 100% match. This is known as a context match. In case the segment is the first or last segment in the file, it might be handled differently.

The matches can also be “fuzzy” matches when there is a partial match. The TM gives each fuzzy match a percentage rating according to how major the differences are. The translator needs to consider each fuzzy match translation to see if it needs to be redone entirely to fit the new context, if it can be used with a small change or two, or if it can be used without changes.

Usually there is also some material that returns no matches. Then the translator needs to create a new translation, just as if they were working without TM support. Each completed translation project adds to the data stored in the TM, reducing the need for completely new translations when working with the same project, customer, or subject in the future.

Clients pay the most for segments that are entirely new translations and less for segments that have fuzzy matches. However, in some cases the fuzzy match isn’t usable in the current context and the rework merits the full price. Projects can set a limit, for example, 65%, below which fuzzy matches are considered new translations. Finally, clients usually pay the least or nothing for segments that have perfect matches.

## Maintaining translation memories

Translation memories tend to contain translations that are no longer useful over time. The two most common reasons for this are probably:

- Inconsistent or duplicate translations for the same source language string
- Terminology changes on the customer’s end

The first situation can happen when multiple translation vendors are used over multiple projects and the TMs are merged without proper maintenance. A company merger can also cause this when their translation assets are combined.

The second situation is a natural outcome of continuous product development and updates. Terminology changes over time even if there are no flaws as such. It’s common that a company’s terminology database is not in sync with its TMs.

TMs are an asset that requires maintenance and investment, just like your product’s code. If you think of TMs as something that is created once and then left alone, your TMs will become less and less useful over time which will incur extra costs when it causes problems during localization. Whether it’s your translation vendor doing the maintenance or your own company, you should include TM upkeep in your localization plans.

This maintenance might involve the following steps:

- Combining entries where the source or target differ in punctuation, spacing, and misspellings.
- Combining entries where there are multiple translations for the same source segment, but only if the source is used in the same context.
- Updating segments to match the latest approved terminology.
