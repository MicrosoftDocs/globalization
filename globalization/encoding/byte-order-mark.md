---
title: Byte Order Mark
description: Byte Order Mark (BOM) is used to indicate how a processor places serialized text into a sequence of bytes.
ms.assetid: ba9afff8-782e-43df-9053-f1f61c8d22eb
ms.date: 03/11/2017
---

# Byte Order Mark

Another concept to be familiar with as you work with Unicode is that of byte-order marks (BOM). A BOM is used to indicate how a processor places serialized text into a sequence of bytes. If the least significant byte is placed in the initial position, this is referred to as "little-endian," whereas if the most significant byte is placed in the initial position, the method is known as "big-endian." A BOM can also be used as a reference to identify the encoding of the text file. Notepad, for example, adds the BOM to the beginning of each file, depending on the encoding used in saving the file. This signature will allow Notepad to reopen the file later. Table 1 shows byte-order marks for various encodings. The UTF-8 BOM identifies the encoding format rather than the BOM of the document-since each character is represented by a sequence of bytes.


| **Encoding**         |  **Encoded BOM** |
| ---------------------|------------------|
| UTF-8                |  EF BB BF        |
| UTF-16 big-endian    |  FE FF           |
| UTF-16 little-endian |  FF FE           |
| UTF-32 big-endian    |  00 00 FE FF     |
| UTF-32 little-endian |  FF FE 00 00     |

**Table 1:** Binary representation of the byte-order mark (U+FEFF) for specific encodings.


