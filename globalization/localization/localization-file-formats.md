---
title: Localization file formats
description: This article describes XML Localization Interchange File Format (XLIFF) in more detail.
author: m-kauppinen
ms.author: v-mikau
ms.topic: conceptual #Required; leave this attribute/value as-is.
ms.date: 07/12/2023

---

# Localization file formats

Computer-aided translation (CAT) tools use a variety of file formats both standardized and proprietary. This topic discusses the standardized interchange formats XML Localization Interchange File Format (XLIFF), TermBase eXchange (TBX), and Translation Memory eXchange (TMX).

## XLIFF

XLIFF is commonly used to exchange data between different CAT tools. It is an XML-based format that pairs the source and target language strings of each segment for content that is being translated. The latest version, XLIFF 2.0, is defined by [ISO 21720:2017](https://www.iso.org/obp/ui/#iso:std:iso:21720:ed-1:v1:en).

XLIFF  gives you a single file format that can be used when translating source files. When translatable text content is extracted from the source files and stored in the XLIFF format, translators can use whichever tools they like to work with the text without worrying about the source’s format or layout. After the translation is ready, the XLIFF files are used to “reassemble” the source files with the new language.

For more information, refer to [Exchanging localizable resources](exchanging-localizable-resources.md).

### Description of the XLIFF format

An XLIFF file contains elements for source and target segment pairs within a translation unit element. A translation unit may be a single word, a sentence, or even a paragraph. The larger the translation unit, the more meaningful, or idiomatic, the translation tends to be. However, if translation units get too long, there's less chance of finding a complete match for the source segment in the translation memory (TM).

An XLIFF file starts with one or more \<file> elements. The \<file> element can contain attributes that specify information like the original file name. Each \<file> element can contain a reference to the skeleton document. Each \<file> element also contains one or more \<unit> elements, and the \<unit> elements contain the \<source> and \<target> elements for each segment.

Here's a simple example of an XLIFF 2.0 file containing two translation units:

```xml
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
```

While parsing your content, you might want to pick up more than just the source segments. For example, if the source file format allows annotations, you might want to store these annotations in the exchange format. Translators can then view the annotations, and your CAT tool might support some level of automation based on the annotations. For example, a segment might have a Do Not Translate annotation, which the CAT tool can use to mark the segment as non-translatable.

## TBX

CAT tools often have proprietary formats for storing terminology. If you want to use a terminology list from one CAT tool with another CAT tool, the TermBase eXchange (TBX) format can be used as an interchange format. Like XLIFF, it is an XML-based format that pairs the source and target language strings of a term and includes a definition for the term. The latest version, TBX 3.0, is defined by [ISO 30042:2019](https://www.iso.org/standard/62510.html/).

For more information, refer to [Managing terminology](managing-terminology.md).

### Description of the TBX format

Each terminological concept is wrapped inside a \<termEntry> element. It can contain descriptive and administrative information and notes in addition to the term itself in various languages.

Here's an example of a simple TBX 2.0 file with only one term entry:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<martif  type="TBX" xml:lang="en-US"><martifHeader><fileDesc><titleStmt><title>Microsoft Terminology Collection Export</title></titleStmt>
<sourceDesc><p>Microsoft Terminology Collection</p></sourceDesc></fileDesc></martifHeader>
<text><body>
    <termEntry id="3466_155801">
        <langSet xml:lang="en-US">
            <descripGrp>
                <descrip type="definition">The process of logging on to a computer by means of a network. Typically, a user first interactively logs on to a local computer, then provides logon credentials to another computer on the network, such as a server, that he or she is authorized to use.</descrip>
            </descripGrp>
            <ntig>
                <termGrp>
                    <term id="155801">network logon</term>
                    <termNote type="partOfSpeech">Noun</termNote>
                </termGrp>
            </ntig>
        </langSet>
        <langSet xml:lang="fr-FR">
            <ntig>
                <termGrp>
                    <term id="155807">ouverture de session réseau</term>
                    <termNote type="partOfSpeech">Noun</termNote>
                </termGrp>
            </ntig>
        </langSet>
    </termEntry>
</body></text></martif>
```

## TMX

Translation Memory (TM) stores translation and linguistic data in a structured format. Translation Memory eXchange (TMX) is the primary format for exchanging TM data between CAT tools. Like the other interchange formats, it is XML-based. The latest version, TMX 1.4b, is defined in [TMX 1.4b (gala-global.org)](https://www.gala-global.org/tmx-14b). TMX 1.4b dates back to 2005.

TMX is a widely used format. For example, the European Union has released some public TMs that cover more than 20 languages in the TMX format. For more information, refer to the [EU Science Hub Language Technology Resources page](https://joint-research-centre.ec.europa.eu/language-technology-resources_en).

### Description of the TMX format

A TMX file consists of a header and a body. The header section contains basic information about the TMX file, for example, the source language and the tool used to create the file. The body section contains all the TM data, divided into translation units with \<tu> elements. Each translation unit consists of a source text segment (\<seg>) and the corresponding translated segments. Each segment is wrapped in a translation unit variant element (\<tuv>).

Here's a simple example of a TMX file that has only one translation unit:

```xml
<tmx version="1.4">
  <header
    creationtool="XYZTool" creationtoolversion="1.01-023"
    datatype="PlainText" segtype="sentence"
    adminlang="en-us" srclang="en"
    o-tmf="ABCTransMem"/>
  <body>
    <tu>
      <tuv xml:lang="en">
        <seg>Hello world!</seg>
      </tuv>
      <tuv xml:lang="fr">
        <seg>Bonjour tout le monde!</seg>
      </tuv>
    </tu>
  </body>
</tmx>
```
