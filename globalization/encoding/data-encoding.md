---
title: Data Encoding
description: The correct encoding is critical to maintain the data integrity to globalize the application.
ms.assetid: 70fa1c6a-da6d-4285-8293-68d9c7b491ef
ms.topic: navigation
ms.date: 03/16/2016
---

# Data Encoding

[Encoding overview](encoding-overview.md)  
Most of the newer software languages and operating systems use Unicode by default.
However, there are languages (such as C++) where developers must pay extra attention to the data encoding.

[Transformations of Unicode code points](transformations-of-unicode-code-points.md)  
Different techniques (UTF-8, UTF-16, UTF-32) to encode the Unicode characters.

[Byte Order Mark (BOM)](byte-order-mark.md)  
The Byte Order Mark is used to indicate how a processor places serialized text into a sequence of bytes, or serves as an encoding file signature.

[Surrogate pairs](surrogate-pairs.md)  
Since Unicode 3.01, more characters are supported beyond the Basic Multilingual Plane (BMP), and the new characters are encoded at the code position U+10000 or higher.

[Code pages](code-pages.md)  
A code page is a list of selected characters represented as code points in a certain order.
Code pages are usually defined to support specific languages or groups of languages that share common writing systems.
