---
title: Maintaining a translation memory (TM)
description: A translation memory (TM) represents a significant asset that demands careful maintenance.
ms.date: 01/01/2022
--- 

# Translation memories

Translation memories (TMs) provide a means for reusing translations. A TM is a store of source and target segment pairs for a set of translations from one or more pieces of translation work. When you pass a source file to the XLIFF editor [Willie: (or other TM-savvy editor)?] and connect to the TM, the system finds all the matches for the segments, and loads them into the editor. These matches can be in-context exact matches (conventionally labeled 101%), exact matches just of the source segment itself (100%), or partial ("fuzzy")&mdash;for example, 75% if six of eight words match. If less than half of the words match, the segment is labeled a "No match." This match percentage labeling is all done at run-time. 

TMs give the translator a head start. Most CAT tool editors allow translators to hide all in-context matches. They then need only inspect the 100% matches, complete the fuzzy matches, and translate the segments that have no match. When you do incremental releases, your translation memories can immediately recreate where the release started from. Then you need to translate only the new or modified content.

TMs can be used by CAT tools, as a pre-processing step, to analyze how much work the translator faces. Most CAT tools have a word counting program that analyzes the document. The analysis counts the number of matches of the different types and reports the number of words in each category. This report can be used to estimate the cost of the translation.

TMs can be connected to other TMs. A translator typically connects directly to a working TM, to which the translator can save translations. This working TM can in turn be connected to read-only "background" TMs. The background TM matches can be assigned premiums or penalties that are computed into the match percentage when matches from them are offered to translators. More than one translation can be offered for a given source segment. When multiple matches are found among the TMs, the one with the highest match percentage is offered first.

In addition to TMs getting populated by translators saving their translation in the TM, you can import data from other TMs. You can also use an alignment tool to align a previously translated source file and the translated version, and import the aligned segments into a TM.

Your TMs should be maintained in a library, named and organized to make it easy to find the appropriate TMs for a project.

## Translation Memory eXchange (TMX)

TMs are stored in TMX files. TMX files comprise entries consisting of aligned segments of text in two or more languages. These entries are translation unit (\<*tu*\>) elements. Within the translation units are translation unit variant (\<*tuv*\>) elements that contain the segment (\<*seg*\>) elements that contain the source and target text. The file also contains a header (\<*header*\>) element that contains information related to the whole file.

### Metadata

A TM is more than just source/target text pairs; it also contains metadata at both the whole TM level and at the segment pair level. At the TM level, you can add metadata to the header section for project, client, domain, subject, and description.

During translation, at the translation unit level, the TM tool may save metadata such as:

- the name of the translator
- the date of translation
- the status of the translation
- match percentage
- linguistic assets used

The linguist maintaining the TM can also add guidance notes, via the \<*note*\> and \<*prop*\> elements. The name of the TM is displayed during translation for the translation unit (since the translator may be connected to multiple TMs). If the project manager has enabled context matching for the TM, the preceding and succeeding segments will be stored as metadata for the segment pair. If the TM has machine translation (MT) entries, the name of the MT engine is indicated. For software localization, some layout formatting, dialogs and menus, and version control can be included.

### Exchanging content

As discussed in [Localization file formats](localization-file-formats.md), the exchange of data in a translation project is often done through the interoperability of three XML formats: TMX for translation memories, TBX for terminology lists, and XLIFF. Some CAT tools have their own native TM format. For example, Trados has a variant called SDLTM. However, TMX is the industry standard, and CAT tools that are presented with other variants, like SDLTM, have to convert them. Because of its XML format, TMX files are transportable. They can be exported, and imported into other TMs. You can also import TBX file data into TMX files.

## Populating TMs

There are several ways to populate a TM:

- Translators can save their translations to the TM they're directly connected to, either as they translate segments (after a review) or in bulk.
- You can import entries from other TMs.
- You can use an alignment tool to align a previously translated source file and the translated version, and import the aligned segments into a TM.
- You can edit the TM directly with a CAT tool for TM editing.

As translators save their translations to a TM, the TM grows. TMs can be set to overwrite translation units that have identical source segments. Or the TM can be set instead to add the new translation, since the same source segment can have different translations, given the context. The TM can also be set to store the preceding and succeeding segments as metadata, so the translation that matches the context will be given priority. Translators can add notes to the translation unit. These notes can be notes for the reviewer or descriptive notes for the TM entry. In addition to the metadata that gets generated automatically for a translation unit, translators and reviewers can set metadata like approval status.

When you import translation units into a TM from another TM, most systems allow you the choice of overwriting vs. adding when the source segments are identical. You might also have the option of which metadata to import.

You can populate a TM by running an alignment tool over already translated source and target language files. The tool will make an initial alignment pass. Then a project engineer can adjust any misalignments. When the alignment is satisfactory, the tool can create a TM comprising the aligned segments.

Most CAT tools have a TM editor. These editors allow you to edit, add and delete translation units. You can edit tags and metadata, not just text. You can filter and sort.

## Types of TMs

TMs can have different uses. A translator typically connects to what can be called a working TM. The working TM can start as an empty TM, or be a copy of a more finalized TM in your TM library. When the translations have been reviewed and approved, the working TM entries can be saved in a library TM. Or the working TM can be saved as a new TM, to be used in follow-on projects. 

To improve your range of translation offerings, most CAT tools allow the translator to connect to one or more background TMs. Also called reference TMs, these read-only TMs might be primary TMs for other products that have similarities to the product for your project. Because they aren't for your current product, matches from these background TMs will usually have penalties added to their match percentage score.  

## Machine translation and TMs

Most CAT tools support the offering of machine translation (MT) segments. Some tools allow the editor to connect directly to an MT engine, tagging the segment as coming from MT on the fly. Particulars of this MT usage should be written into the agreement between the provider and client. Other tools allow you to incorporate the machine translations into TMs themselves. Those TMs are read-only and store only machine translations. When a machine translation is loaded into a segment, it's tagged as originating from an MT engine. MT TMs are typically populated during cleanup of machine translated XLIFF files. Because these machine translations have been improved by translators, the matches from an MT TM are likely to be better than the original machine translation.

## TM maintenance

Over time, as TMs get used and added to, they can become polluted with conflicting TUs, misalignments, duplicates, obsolete translations, and so on. Maintenance of the library requires systematic attention by a linguist.

Most TM management systems support the following maintenance features:

- Edit TM, including batch operations
- Reindex the TM, to speed up lookups
- Identify duplicate TUs (with option to batch delete)
- Identify terminology mismatches among TUs
- Lock/unlock segments
- Global search and replace
- Filter entries by date, translator, status, and other metadata
- Export and import TM
- Backup TM

Duplicates, where identical source segments have different translations, can be tricky. Because some segments might have more than one legitimate translation, you should avoid using bulk operations to clean up duplicates. You would eliminate the duplicate entries, but you might lose some legitimate translations doing that. Before doing a bulk delete, you should identify the legitimate alternative translations and tag them so you can export just them to a file, then you can import them after you've used the other technique to purge the unwanted duplicates.

There are two common issues with terminology in TMs. There can be mismatches, where a translated term differs among TUs. Also, TMs can contain terms that differ from the term validated in the current corporate terminology list. It's cost-effective to fix these inconsistencies in the TMs, rather than to pass the responsibility on to LSPs and their translators. The development of terminology lists should happen early in the product life cycle. As changes are made to the terminology lists, the changes should be reflected in the TMs as part of TM maintenance.

Translation memories store the history of the TUs as metadata. This history includes the name of the original translator, the date of the translation, any modification date (and the name of the modifier), the source and target languages, the tool that created the TM, and other information. A translation unit can have other metadata, like a note to indicate the context of the segment and a status indicator. All of this metadata can be filtered on to expedite TM maintenance.

Like your product itself, you want your TMs to be consistent with your corporate style guide. To avoid reintroducing style inconsistences to your localized products, you should use a TM editor to normalize your source and your translations. If you enforce consistent language and punctuation in the TMs, you eliminate the risk of pollution of the translations.

## Translation management systems

A translation management system (TMS) can automate your workflow, managing tasks like:

- file delivery and pickup
- translation status/progress
- resource assignment
- review
- quality assurance
- production
- sign-off
- delivery

A TMS can even assist with the library maintenance. Project managers can monitor and control all phases of the translation life cycle. Translators can pick up and drop off the files they work on. Notifications are sent to task owners and project managers as tasks are ready to start, completed, or running behind. While a CAT tool is different from a TMS, the TMS usually can link to TMs, terminology lists, and the translation editor that the CAT tool comprises. The major players in the localization industry have developed their own CAT tools and TMS. This way, there's a synergy in which the tools have a harness in which to operate. 

The TMS should be centralized such that providers and clients can both access it. Project managers at the client (the LSP) need to see the progress status of tasks, as do project managers at the provider. The different roles will have different permissions in the system. Translators should be able to see and perform only their own tasks. Project managers, both at the provider and client, need to see and to respond to the entire workflow. Because the TMS will reside, probably, in the product owner's cloud space, a careful permission system is required. The cloud space allows translation memories to be shared in real time. A translation saved to the TM by a translator in one continent can be immediately available to a translator across the globe.

## Next steps
<!-- Add a context sentence for the following links -->
- [Managing terminology](managing-terminology.md)
- [Localize software](localize-software.md)
- [Content localization](localize-content.md)