---
title: Tranformations of Unicode Code Points
description: Brief description about the techniques to encode Unicode characters.
ms.assetid: 6b8a5c90-424f-4254-9c98-8311e1f53594
ms.date: 03/11/2017
---

# Transformations of Unicode Code Points

There are different techniques to represent each one of the Unicode code points in binary format. Each of the following techniques uses a different mapping to represent unique Unicode characters. The Unicode encodings are:

-   **UTF-8:** To meet the requirements of byte-oriented and ASCII-based systems, UTF-8 has been defined by the Unicode Standard. Each character is represented in UTF-8 as a sequence of up to 4 bytes, where the first byte indicates the number of bytes to follow in a multibyte sequence, allowing for efficient string parsing. UTF-8 is commonly used in transmission via Internet protocols and in Web content.
-   **UTF-16:** This is the 16-bit encoding form of the Unicode Standard where characters are assigned a unique 16-bit value, with the exception of characters encoded by surrogate pairs, which consist of a pair of 16-bit values. The Unicode 16-bit encoding form is identical to the International Organization for Standardization/International Electrotechnical Commission (ISO/IEC) transformation format UTF-16. In UTF-16, any characters that are mapped up to the number 65,535 are encoded as a single 16-bit value; characters mapped above the number 65,535 are encoded as pairs of 16-bit values. (For more information on surrogate pairs, see "[Surrogate Pairs](https://msdn.microsoft.com/globalization/mt683846)".) UTF-16 little-endian is the encoding standard at Microsoft (and in the Windows operating system).
-   **UTF-32:** Each character is represented as a single 32-bit integer.

The table below shows two characters encoded in both code pages and Unicode, using UTF-16 and UTF-8.

| Character |  **A**  | **院**     |
|-----------|-------|----------|
| MBCS      |  41   | 89 40    |
| UTF-16    |  0041 | 9662     |
| UTF-8     |  41   | E9 99 A2 |

**Table 1:** The character "A" and the CJK character encoded in code pages and in Unicode with both UTF-16 and UTF-8.

Since UTF-8 is so commonly used in Web content, it's helpful to know how Unicode code points get mapped into this encoding without introducing the hassle of MBCS characters. Table 2 shows the relationship between Unicode code points and a UTF-8-encoded character. The starting byte of a chain of bytes in a UTF-8 encoded character tells how many bytes are used to encode that character. All the following bytes start with the mark "10" and the xxx's denote the binary representation of the encoding within the given range.

|Unicode Range     |UTF-8 Encoded Bytes                                  |
|------------------|-----------------------------------------------------|
|0x0000-0x007F     |**0** xxxxxxx                                        |
|0x0080-0x07FF     |**110** xxxxx **10**xxxxxx                           |
|0x0800-0xFFFF     |**1110** xxxx **10**xxxxxx **10**xxxxxx              |
|0x10000-0x1FFFFF  |**11110**xxx **10**xxxxxx **10**xxxxxx **10**xxxxxx  |

**Table 2:** Relationship between Unicode code points and a UTF-8-encoded character. In UTF-8, the first byte indicates the number of bytes to follow in a multibyte-encoded sequence.


