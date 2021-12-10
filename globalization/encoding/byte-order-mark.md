---
title: Byte order mark
description: Byte Order Mark (BOM) is used to indicate how a processor places serialized text into a sequence of bytes.
ms.assetid: ba9afff8-782e-43df-9053-f1f61c8d22eb
ms.date: 03/11/2017
---

# Byte order mark

Another concept to be familiar with as you work with Unicode is that of byte-order mark (BOM).
A BOM is used to indicate how a processor places serialized text into a sequence of bytes.
If the least significant byte is placed in the initial position, this is referred to as "little-endian," whereas if the most significant byte is placed in the initial position, the method is known as "big-endian."

A BOM can also be used as a file signature to identify the encoding of a text file, in addition to the byte order.
Notepad, for example, may add a file signature to the beginning of each file, depending on the encoding used in saving the file.
This signature allows Notepad to reopen the file later with the correct interpretation of the bytes as Unicode, versus some unknown, implicit, and ambiguous code page.

Table 1 shows the byte-order marks for various encodings.
The UTF-8 file signature (commonly also called a "BOM") identifies the encoding format rather than the byte order of the document.
UTF-8 is a linear sequence of bytes and not sequence of 2-byte or 4-byte units where the byte order is important.

| **Encoding**         |  **Encoded BOM** |
| ---------------------|------------------|
| UTF-8                |  EF BB BF        |
| UTF-16 big-endian    |  FE FF           |
| UTF-16 little-endian |  FF FE           |
| UTF-32 big-endian    |  00 00 FE FF     |
| UTF-32 little-endian |  FF FE 00 00     |

**Table 1:** Binary representation of the byte-order mark (U+FEFF) for specific encodings.
