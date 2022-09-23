---
title: Maintaining a translation memory (TM)
description: A translation memory (TM) represents a significant asset that demands careful maintenance.
ms.date: 01/01/2022
--- 

# Translation memories

Translation memories provide a means for reusing translations. The owner of the product should also own the translation memories. Translators create translations and save them to a translation memory (TM). Typically, this translation memory will be a working TM, not the final TM of the product owner. The product owner can then review and merge the new and modified translation units into the final TM. This review must be done before the translations are accepted for delivery. If your translators are considered trustworthy, you might consider having them save instead to the final TM, to cut out the merge process.

It's a good idea for product owners to store both final TMs and the working TMs in your TM library. This way if problems are spotted in the final TM, they can be traced to working TMs. Translation memories store the history of the TUs as metadata. This history includes the name of the original translator, the date of the translation, any modification date (and the name of the modifier), the source and target languages, the tool that created the TM, and other information. A translation unit (TU) can have other metadata, like a note to indicate the context of the segment and a status indicator.

When a translator opens a document to translate, using a CAT tool, the system looks up each source segment in the TM and when it finds an exact match, offers that match to the translator. The offering is labeled an exact, or 100% match. You can configure most TM systems to store not only the translated segment itself, but also the preceding and succeeding segments (as metadata). With that configuration, the system looks at not just the current segment, but the preceding and succeeding segments. If all three segments match exactly, the translation offered is labeled a context, or 101% match. If the system can't find an exact match for the source segment, but only a partial (fuzzy) match, it will offer it, labeling it by the percentage of words matched (for example, 75% if, say, six of eight words match). If less than half of the words match, the segment is usually labeled a "No match." This match percentage labeling is all done at run-time. 

In addition to TMs getting populated by translators saving their translation in the TM, you can import TUs from other TMs. You can also use an alignment tool to align a previously translated source file and the translated version, and import the aligned segments into a TM.

## Metadata

Some metadata for a TM is at project level. Some metadata, at the translation unit (TU) level, is added as the translator works on and saves segments.  

At the project level, there can be metadata for the TM name, type, and version; start and end dates of the project; client and domain; details of work resources assignments. The project manager can also label source segments as non-translatable or add other guidance notes.

During translation the TM tool may save metadata such as the name of the translator, the date of translation, the status of the TU, match percentage, and linguistic assets used. The name of the TM is displayed for the offered translation (since multiple translations can be offered). If the project manager has enabled context matching for the TM, the preceding and succeeding segments will be stored as metadata for the TU. If the TM has machine translation (MT) entries, the name of the MT engine is indicated. TMs may be tagged for specific jobs or reused based on the creation date. For software localization, some layout formatting, dialogs and menus, and version control can be included.

## Exchanging content

As discussed in [Localization file formats](localization-file-formats.md), the exchange of data in a translation project is often done through the interoperability of three XML formats: TMX for translation memories, TBX for terminology lists, and XLIFF. XLIFF is the format the documents to be translated are acted upon in most CAT tool editors. The most common XLIFF file extension is *.xlf*. There are third-party and open source tools that allow you to parse and convert particular file formats to XLIFF. Most CAT tools include their own converters for saving files to XLIFF. These built-in converters have the advantage that the editor they're paired with is designed for that particular variant of XLIFF. In some CAT tools, the conversion to *.xlf* is done in the editor itself, when the translator opens the file.

In addition to loading the *.xlf* file, the editor will load translation memory and terminology matches from the TMX and TBX files to which the translator has connected. The TMX and TBX formats are known by the CAT tool, so no conversion is necessary.

## Machine translation

Most CAT tools support the offering of machine translation (MT) segments. Some tools allow you to incorporate the machine translations into TMs themselves. These tools then tag the segment as originating from an MT engine. Other tools allow the editor to connect directly to an MT engine, tagging the segment as coming from MT on the fly. Particulars of this MT usage should be written into the agreement between the provider and client.

## TM maintenance

If you have lots of products being translated, you'll need a well-organized library of TMs, and you'll have to maintain this library. You'll probably organize this library by product types and TM types. For example, you might have final TMs and associated working TMs. The final TM should have only fully reviewed and approved translation units. Translators can connect to a copy of the primary TM for their working TM. But the working TM translations shouldn't be merged into the final TM until every translation unit has been reviewed and approved.

You should name your TMs accordingly, by product, version, and TM type, so you can quickly locate the appropriate TM to use for the next version of a product. Over time, as TMs get used and added to, they can become polluted with conflicting TUs, misalignments, duplicates, obsolete translations, and so on. Maintenance of the library requires systematic attention by a linguist.

Most TM management systems support the following maintenance features:

- Edit TM, including batch operations
- Reindex the TM, to speed up lookups
- Identify duplicate TUs (with option to batch delete)
- Identify terminology mismatches among TUs
- Global search and replace
- Filter entries by date, translator, status, and other metadata
- Export and import TM
- Backup TM

Duplicates, where identical source segments have different translations, can be tricky. Because some segments might have more than one legitimate translation, it might be risky to use the bulk technique of exporting the TM, then deleting its contents, then importing the exported TM with a setting that imports only the most recent TUs. You would eliminate the duplicate entries, but you might lose some legitimate translations doing that. Before doing a bulk delete, you should identify the legitimate alternative translations and tag them so you can export just them to a file, then you can import them after you've used the other technique to purge the unwanted duplicates.

There are two common issues with terminology in TMs. There can be mismatches, where a term differs among TUs. Also, TMs can contain terms that differ from the term validated in the current corporate terminology list. It's cost-effective to fix these inconsistencies in the TMs, rather than to pass the responsibility on to LSPs and their translators. The development of terminology lists should happen early in the product life cycle. As changes are made to the terminology lists, the changes should be reflected in the TMs as part of TM maintenance.

## Translation management systems

A translation management system (TMS) can automate your workflow, managing tasks like file delivery and pickup, translation status/progress, resource assignment, review, quality assurance, production, sign-off, and delivery. A TMS can even assist with the library maintenance. Project managers can monitor and control all phases of the translation life cycle. Translators can pick up and drop off the files they work on. Notifications are sent to task owners and project managers as tasks are ready to start, completed, or running behind. While a CAT tool is different from a TMS, the TMS usually can link to TMs, terminology lists, and the translation editor that the CAT tool comprises. The TMS should be centralized such that providers and clients can both access it. Project managers at the client (the LSP) need to see the progress status of tasks, as do project managers at the provider. The different roles will have different permissions in the system. Translators, should be able to see and perform only their own tasks. Project managers, both at the provider and client, need to see and to respond to the entire workflow.

## TMs and translation

Translation memories can store the entirety of a bilingual file. If you lose the translated file, you could pass the source file to the XLIFF editor, connect to the TM, and it would find matches for all the segments and load them into the editor. You could then, as you did before, back convert the target segments to their original format and you would have recreated the translated file that you lost. It's rare to lose a target file, but this example goes to show how when you do incremental releases, your translation memories can immediately recreate where the release started from. Then you need to translate only the new or modified content.

TMs can be used to analyze how much work the translator faces. Most CAT tools have a word counting program that analyzes the document. The analysis counts the number of in-context matches, 100% matches, fuzzy (that is, partial) matches, repetitions, no match found, and even machine translations. The analysis reports the number of words in each category. This report can be used to estimate the cost of the translation.

The primary function of a TM is to offer suggested translations to the translator for each segment. Most CAT tool editors allow translators to hide all in-context matches. They then need only inspect the 100% matches, complete the fuzzy matches, and translate the segments that have no match.  As translators work in the CAT tool, they can save their translations to the TM, so the translations can be reused in future projects. Increasingly, CAT tools store and serve the translations in the cloud. The cloud allows a translation saved by a translator in one place to become immediately available to translators in other places, promoting consistency across a large project.

TMs can be connected to other TMs. A translator typically connects directly to a working TM, to which the translator can save translations. This working TM can in turn be connected to read-only "background" TMs. The background TM matches can be assigned premiums or penalties that are computed into the match percentage when matches from them are offered to translators. More than one translation can be offered for a given source segment. When multiple matches are found among the TMs, the one with the highest match percentage is offered first.

## Next steps
<!-- Add a context sentence for the following links -->
- [Managing terminology](managing-terminology.md)
- [Localize software](localize-software.md)
- [Content localization](localize-content.md)