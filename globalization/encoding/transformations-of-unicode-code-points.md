---
title: Transformations of Unicode code points
description: Summary of the techniques to encode Unicode characters.
ms.assetid: 6b8a5c90-424f-4254-9c98-8311e1f53594
---

# Transformations of Unicode code points

There are different techniques to represent each of the Unicode code points in binary format.
Each of the following techniques uses a different mapping to represent unique Unicode characters.
The Unicode encodings (transformation formats) are:

- **UTF-8:** To meet the requirements of byte-oriented and traditionally ASCII-based systems, UTF-8 has been defined by the Unicode Standard.
Each character is represented in UTF-8 as a sequence of up to 4 bytes, where the first byte indicates the number of bytes to follow in a multi-byte sequence, allowing for efficient data parsing.
UTF-8 is commonly used in transmission via Internet protocols and in Web content.

- **UTF-16:** This is the 16-bit encoding form of the Unicode Standard where characters are assigned a unique 16-bit value, with the exception of characters encoded by surrogate pairs which consist of a pair of 16-bit values.
The Unicode 16-bit encoding form is identical to the International Organization for Standardization/International Electrotechnical Commission (ISO/IEC) transformation format UTF-16.
In UTF-16, any characters that are mapped up to the number 65,535 are encoded as a single 16-bit value; characters mapped above the number 65,535 are encoded as pairs of 16-bit values.
For more information on surrogate pairs, see "[Surrogate Pairs](surrogate-pairs.md)".
UTF-16 little-endian (UTF-16LE) is the encoding standard in the Windows operating system.

- **UTF-32:** Each character is represented as a single 32-bit integer.

The table below shows two characters encoded in a code page and Unicode, using UTF-16, UTF-32, and UTF-8.

| Encoding |  **A**  | <span lang="zh-Hans">**院**</span> | Byte Count |
|----------|---------|------------------------------------|------------|
| MBCS     | 41       | 89, 40     | 2 |
| UTF-8    | 41       | E9, 99, A2 | 3 |
| UTF-16   | 0041     | 9662       | 2 |
| UTF-32   | 00000041 | 00009662   | 4 |

**Table 1:** The character "A" and the CJK character encoded in code pages and in Unicode with both UTF-16 and UTF-8.

Since UTF-8 is so commonly used in Web content, it's helpful to know how Unicode code points get mapped into this encoding.
Table 2 shows the relationship between Unicode code points and their UTF-8 encoding.
The starting byte of a sequence of bytes in a UTF-8 encoded character tells how many bytes are used to encode that character.
All the following bytes start with the bits `10` and the x's denote the binary representation of the encoding within the given range.

| Unicode Code Point Range | UTF-8 Encoded Bytes (binary) |
|-------------------------|---------------------|
| `0x00000000-0x0000007F` | **`0`**`xxxxxxx` |
| `0x00000080-0x000007FF` | **`110`**`xxxxx`, **`10`**`xxxxxx` |
| `0x00000800-0x0000FFFF` | **`1110`**`xxxx`, **`10`**`xxxxxx`, **`10`**`xxxxxx` |
| `0x00010000-0x0010FFFF` | **`11110`**`xxx`, **`10`**`xxxxxx`, **`10`**`xxxxxx`, **`10`**`xxxxxx` |

**Table 2:** Relationship between Unicode code points and their UTF-8-encoded representation.

## More information

- [Unicode Standard - 2.5 Encoding Forms](https://www.unicode.org/versions/Unicode14.0.0/ch02.pdf#G13708)
- [Unicode Standard - 3.9 Unicode Encoding Forms](https://www.unicode.org/versions/Unicode14.0.0/ch03.pdf#G7404)
- [Unicode Technical Report 17 - UNICODE CHARACTER ENCODING MODEL](https://www.unicode.org/reports/tr17/)