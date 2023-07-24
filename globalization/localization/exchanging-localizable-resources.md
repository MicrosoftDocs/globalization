---
title: Exchanging localizable resources
description: This article describes XML Localization Interchange File Format (XLIFF) in more detail.
author: m-kauppinen
ms.author: v-mikau
ms.topic: conceptual #Required; leave this attribute/value as-is.
ms.date: 07/12/2023

---

# Exchanging localizable resources

XML Localization Interchange File Format (XLIFF) and other standardized interchange formats are introduced in the article [Localization file formats](localization-file-formats.md). This article discusses some aspects of XLIFF in more detail.

## Parsing and reassembling source files

When translating, it is preferable to separate translatable text from non-translatable elements like document layout and markup. This process of isolating translatable text content from the source files is known as extraction. Extracting the translatable content from the source files lets the translators work with only the text without worrying about the source file format or the layout within each source file.

XLIFF  is a file format that can be used when translating source files regardless of what proprietary format they might use. XLIFF stores the source text and the corresponding translation in an XML format that facilitates transferring the translatable content through the various stages of the translation workflow.

Computer-aided translation (CAT) tools have parsers for isolating translatable text from document layout and storing the text in the XLIFF format. These parsers support common source file formats such as HTML and other markup languages, RTF, Microsoft Office products, Adobe InDesign, Adobe FrameMaker, and plain text. The non-translatable material is stored in separate files called skeletons. For more information, refer to [Parsing source files to XLIFF](#parsing-source-files-to-xliff).

After the translation is complete and the translated target language strings have been added to the XLIFF files, the skeleton files are used for reassembling the source file format with the translated content. Then the files are ready for:

- Previewing the translations with the actual layout.
- Testing that your layout still works with the translated text, which is likely of different length and might also use different fonts, be written in the opposite direction, have different pagination, or different word or page wrapping.
- Making the final delivery when the above steps have been completed.

## Parsing source files to XLIFF

When planning a translation project, you need to agree with your translation vendor who will handle the extraction of translatable content from the source files. If you handle it internally, you'll need a tool for converting the source files into the XLIFF format. This tool must understand the source format. Here's an example of an RESX file (used by programs developed with Microsoft's .NET Framework):

```xml
<?xml version="1.0" encoding="utf-8"?>
<root>
  <xsd:schema id="root" xmlns="" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">
    <xsd:import namespace="http://www.w3.org/XML/1998/namespace" />
    <xsd:element name="root" msdata:IsDataSet="true">
    </xsd:element>
  </xsd:schema>
  <data name="ServiceUnavailableInRegion" xml:space="preserve">
    <value>{0} is not available in the {1} region. Please select another region.</value>
    <comment>Where {0} is a service name like "Virtual Machines" and {1} is a region name like "Japan West"</comment>
  </data>
</root>
```

An RESX parser for XLIFF can create an XLIFF file using the strings in each \<value> element of the RESX file. Note that strings in the \<comment> elements of RESX can also be parsed to the \<note> element in XLIFF, which allows developers to include helpful annotations to translators. These annotations could include the values that will be inserted into placeholders at runtime or describe how a string will be used in the UI. Here's an example of the previous RESX file parsed to XLIFF:

```xml
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

Unlike the RESX format, XLIFF has a target element for the translation. The target segments can be populated from translation memory, or by the translator if a previous translation is not available.

## Handling metadata

Localizable resource files can include comments and contextual information for translators. The comments can be very helpful to the translators since they may not know your product. A comment for a string could explain, for example, where the string appears in the user interface and what it relates to. The comment can explain the conditions under which the string is displayed.

As an example, see the parsed XLIFF file above. The \<note> element contains the following explanation for the string:

``Where {0} is a service name like "Virtual Machines" and {1} is a region name like "Japan West".``

This lets the translators know how {0} and {1} are used in this context.

If the string contains technical terms or application jargon, the usage should be explained as well. If the string is a format string containing placeholders, it's important to document the part of speech and meaning of each placeholder.

Many computer-aided translation (CAT) tools can display these comments next to the translatable segment.
