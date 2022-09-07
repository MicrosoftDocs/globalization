---
title: Localization file formats
description: This article helps you understand the different data interchange formats and source formats in localization projects.
author: v-williamsw
ms.author: v-williamsw
ms.date: 09/07/2022
---

# Localization file formats

Interchange formats:
XLIFF
TMX
TBX
 
Source formats:
RESX
JSON
Java .properties
(any other source format including XML)
 
For translation using XLIFF, you need to convert the source format into XLIFF using a parser. While parsing the content, you might want to pick up more than just the source segments; for example, if the source file format allows annotations/comments, you might want to store these annotations/comments in the XLIFF (for example, the <note> element) so translators can view the annotations/comments, or so that your TM tool can automatically process based on these annotations/comments (for example, setting the translate attribute of <trans-unit>). I don't think that you have to cover every source file format, but you might want to mention some common source file formats for code (Resx, json, .properties), content (Markdown, Word, Excel, FrameMaker), etc.
 
I think that the topic would be structured something like:
XLIFF
      What is it
      Why use it
      History
      Standard (e.g. ISO)
      Simple description of the spec
            An example of an XLF file showing translations
      Parsing source to XLIFF
            Handling comments - you could use RESX as an example as it can have a <value> and a <comment> node in each <data> element.
TBX
      ...
TMX
      ...