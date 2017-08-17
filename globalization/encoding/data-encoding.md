---
title: Data Encoding
description: The correct encoding is critical to maintain the data integrity to globalize the application.
ms.assetid: 70fa1c6a-da6d-4285-8293-68d9c7b491ef
ms.date: 03/16/2016
---

# Data Encoding

[Encoding Overview](encoding-overview.md)  
Most of the newer software languages support using Unicode by default. However, there are languages (such as C++) where the developers need to pay extra attention to the data encoding.

[Transformations of Unicode Code Points](transformations-of-unicode-code-points.md)  
Different techniques (UTF-8, UTF-16, UTF-32) to encode the Unicode characters.

[Byte Order Mark](byte-order-mark.md)  
The Byte Order Mark (BOM) is used to indicate how a processor places serialized text into a sequence of bytes.

[Surrogate Pairs](surrogate-pairs.md)  
Since Unicode 3.01, more characters are supported beyond the BMP, and the new characters are encoded at the code position U+10000 or higher.

[Code Pages](code-pages.md)  
A codepage is a list of selected character codes characters represented as code points) in a certain order. Codepages are usually defined to support specific languages or groups of languages that share common writing systems. All Window codepages can only contain 256 code points.


