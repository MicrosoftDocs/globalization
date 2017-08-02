This documentation is archived and is not being maintained.

# Data Encoding

[](https://msdn.microsoft.com/en-us/library/mt683841)
## Encoding Overview

Most of the newer software languages support using Unicode by default. However, there are languages (such as C++) where the developers need to pay extra attention to the data encoding.

[](https://msdn.microsoft.com/en-us/library/mt683843)
## Transformations of Unicode Code Points

Different techniques (UTF-8, UTF-16, UTF-32) to encode the Unicode characters.

[](https://msdn.microsoft.com/en-us/library/mt683845)
## Byte Order Mark

The Byte Order Mark (BOM) is used to indicate how a processor places serialized text into a sequence of bytes.

[](https://msdn.microsoft.com/en-us/library/mt683846)
## Surrogate Pairs

Since Unicode 3.01, more characters are supported beyond the BMP, and the new characters are encoded at the code position U+10000 or higher.

[](https://msdn.microsoft.com/en-us/library/mt662301)
## Code Pages

A codepage is a list of selected character codes characters represented as code points) in a certain order. Codepages are usually defined to support specific languages or groups of languages that share common writing systems. All Window codepages can only contain 256 code points.


