---
title: Content localization
description: In addition to software localization, content localization is an integral part of adapting a product for a particular market. 
---

# Content localization

In addition to software localization, content localization is an integral part of adapting a product for a particular market.
Content localization includes user-assistance (UA) documentation, which consists of printed documentation, online content, and Help.
Content can be actual pieces of the software product or an online product by itself.

Software localization involves different methods than those used for content localization.
One of the most obvious differences between localizing content and localizing software is that the Help text often consists of long continuous text that must be translated as one big piece.
Even in the case of an online Help system, there are usually short topics that are connected to each other by hyperlinks.
Each topic page still represents a complete entity in itself that is generally comprehensible to both the reader and to the localizer.
Thus this text can be translated from the first to the last line, sentence after sentence, without the localizer ever having to wonder where a particular string might show up in the product or what it could mean.
This is especially true since this text is designed to serve as documentation and is, by nature, somewhat self-explanatory.

Tracking content changes made in the source is crucial to lowering localization costs.
Instead of having to retranslate the whole document, it is much more efficient to just retranslate those parts of the localized text that have been modified in the source.
Automatic translation tools, which are common for content translation, use a feature called "Translation Memory" to help track content changes.
That is why the content should be written in a way that is compatible with these tools in order to reduce translation errors and proofreading efforts.
The content's text needs to be isolated from the layout and structure tags.
Isolating these tags reduces the possibilities of inadvertently mistranslating something.
The layout needs to be designed in a way that is compatible with the languages into which you are localizing, so that you don't have to make many modifications to tags.
Such general layout design makes the localization job proceed more easily and quickly.

One of the big challenges in localizing online Help and related Web sites is that the original text is often created under a very tight schedule toward the end of the product cycle.
If the localized product is scheduled to ship simultaneously with the original-language product, the documentation has to be localized under an even tighter schedule.
Indeed, adding the localized Help to the build is often one of the last things to be done before a localized product is shipped, which does not leave much room for testing.
And while there is little chance of the localized Help breaking functionality within the product itself, you still want to be sure that all the links that connect the different Help pages still work.
