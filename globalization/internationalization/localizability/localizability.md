This documentation is archived and is not being maintained.

# Localizability

[](https://msdn.microsoft.com/en-us/library/mt651700)
## Localizability Overview

Localizability is the process/practice to enable the software to be localized into different languages without any change to the source code.

[](https://msdn.microsoft.com/en-us/library/mt662338)
## Isolate Localizable Resources

The easiest way to deal with localizable resources is to put everything in some type of resource repository, such as Windows resource files, .NET assemblies files, or a database when dealing with Web content.

[](https://msdn.microsoft.com/en-us/library/mt662339)
## String Handling

There are many challenges to handle the strings that need to be localized. Please see the details for the 5 best practices.

[](https://msdn.microsoft.com/en-us/library/mt662340)
## Mirroring Awareness

For Right-To-Left (RTL) languages, not only does the text alignment and text reading order go from right to left, but also the UI elements layout should follow this natural direction of going from right to left.

[](https://msdn.microsoft.com/en-us/library/mt662341)
## UI Considerations

UI elements may need to be re-sized for the localized software. The developer should consider the localized strings could be (much) longer than the English strings to implement the UI to handle them.


