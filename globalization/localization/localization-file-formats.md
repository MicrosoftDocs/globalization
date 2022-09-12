---
title: Localization file formats
description: This article helps you understand the different data interchange formats and source formats in localization projects.
author: v-williamsw
ms.author: v-williamsw
ms.date: 09/07/2022
---

# Localization file formats

The material that you need translated can be in various source formats. For your software, you might have isolated your translatable strings in RESX, RES, JSON, Java properties, or other file formats. Your documentation might be in HTML, Microsoft Office, or other formats. One option for managing the translation of different source formats is to use an interchange format such as XLIFF. Source files can be parsed to XLIFF.

In addition to XLIFF, many translation tools support TBX as an interchange format for terminology and TMX as an interchange format for translation memory.

## XLIFF

XLIFF is an acronym for XML Localization Interchange File Format. It gives you a single file format for translating different kinds of documents. XLIFF is commonly used by CAT tools to exchange data. It's an XML format and can contain both source and target language versions of a given text. XLIFF pairs the source and target language strings of each segment in the document. XLIFF filters isolate text from the document type layout. CAT tools have parsers for common source file formats: HTML, XML and other markup languages, RTF, Microsoft Office products, InDesign, FrameMaker, plain text, and more. These filters store the non-translatable material in what are called skeletons. The skeleton files are used for reassembling the translated material into the original format for previewing the translations and for final delivery.

The latest version, XLIFF 2.0, is defined by ISO 21720. You can obtain the ISO 21720 XLIFF standard [here](https://www.iso.org/obp/ui/#iso:std:iso:21720).

#### The XLIFF format

An XLIFF file contains tags for source and target segment pairs, within a translation unit element. A translation unit may be a single word, a phrase, one or more sentences, or even a larger unit.

Each translation unit tag has an ID which identifies the location of the text in the original and skeleton file. There are tags for source language and target language, and original file ID and name. The other important tag identifies the skeleton file (a `.skl` file). Here's a simple example of an XLIFF 2.0 file with two translation units:
```
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
The larger the translation unit, the more meaningful, or idiomatic, the translation will tend to be. However, there are problems with making a translation unit too long. With longer units, there's less chance of finding a complete match for the source segment. Furthermore, if the translation unit is so long that there are few units in the document, a minor change would be harder for the translator to detect.

While parsing your content, you might want to pick up more than just the source segments. For example, if the source file format allows instructions, you might want to store these instructions in the exchange format. Translators can then view the instructions, and your TM tool can automatically process based on the instructions. For example, a source segment might have a Do Not Translate instruction, which the tool can set as a Do Not Translate attribute in the interchange format.

### Parsing source to XLIFF

You'll need a tool for converting the source files into XLIFF format. This tool must understand the source format. For source files that are in a markup language format, this process is relatively straight-forward. Here's a simple example of an RESX file:
```
<?xml version="1.0" encoding="utf-8"?>
<root>
  <xsd:schema id="root" xmlns="" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">
    <xsd:import namespace="http://www.w3.org/XML/1998/namespace" />
    <xsd:element name="root" msdata:IsDataSet="true">
    </xsd:element>
  </xsd:schema>
  <data name="ServiceUnavailableInRegion" xml:space="preserve">
    <value>{0} is not available in the {1} region.  Please select another region.</value>
    <comment>Where {0} is a service name like "Virtual Machines" and {1} is a region name like "Japan West"</comment>
  </data>
</root>
```
An RESX parser for XLIFF can create an XLIFF file using the strings in each \<*value*> element of the RESX. Note also that strings in the \<*comment*> elements of RESX can be parsed to the \<*note*> element in XLIFF, which allows developers to supply annotations to translators. These annotations could include the values that might be inserted into placeholders at runtime or might describe how a string will be used in the UI.
```
<?xml version="1.0" encoding="utf-8"?>
<xliff version="1.2">
  <file datatype="resx" source-language="en-US" target-language="zh-TW">
    <header>
      <skl>
        <external-file href="example.skl"
      </skl>
    </header>
    <body>
        <trans-unit id="ServiceUnavailableInRegion">
            <source>{0} is not available in the {1} region. Please select another region.</source>
            <target>{1}地區不提供{0}。請選擇其他地區。</target>
            <note>Where {0} is a service name like "Virtual Machines" and {1} is a region name like "Japan West"</note>
        </trans-unit>
    </body>
  </file>
</xliff>
 ```
Unlike the RESX format, XLIFF has a target element for the translation. The target segments can be populated from a TM or term base, or by the translator.

## TBX

CAT tools often have proprietary formats for storing terminology. If you want to use a terminology list from one CAT tool with another CAT tool, TermBase eXchange (TBX) can be used as an interchange format.  Here's an example of a simple TBX file with only one term entry:
```
<?xml version="1.0" encoding="UTF-8"?>
<martif type="TBX" xml:lang="en-US"><martifHeader><fileDesc><titleStmt><title>Microsoft Terminology Collection Export</title></titleStmt>
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
You can obtain the ISO 30042 TermBase eXchange (TBX) standard [here](https://www.iso.org/standard/62510.html/). See [Managing terminology](managing-terminology.md). 

## TMX

A translation memory (TM) file stores translation and linguistic data in a structured format. Translation Memory eXchange (TMX) is the primary format for exchanging TM data between CAT tools.

Here's a simple example of a TMX file that has only one translation unit:
```
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
See [here](https://www.gala-global.org/tmx-14b) for the specification of the TMX 1.4b format.

## Next steps
<!-- Add a context sentence for the following links -->
- [Managing terminology](managing-terminology.md)
- [Maintaining a translation memory](translation-memories.md)
- [Localize software](localize-software.md)
- [Content localization](localize-content.md)