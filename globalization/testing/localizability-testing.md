---
title: Localizability Testing
description: Localizability testing verifies if UI of the program being tested can be easily translated to any target language without making code modifications.
ms.assetid: 52e11350-bdb0-4086-96b6-ca71f29a21ff
ms.date: 04/05/2017
---

# Localizability Testing

The purpose of localizability testing is to verify that the UI of the program being tested can be easily translated to any target language without re-engineering or making code modifications. Since localizability bugs must be fixed in the code of the application, they must be looked for at the earliest stage of development possible. By doing so, you can circumvent having to fix bugs for every language version at a later point. (See [Designing for Internationalization](https://msdn.microsoft.com/globalization/mt790752).) Paradoxically, however, the problems that cause bugs to appear in the first place usually only become apparent once localization is done. Furthermore, since localization occurs only after the code is complete and reaches a certain degree of stability, there is inevitably a long time span between an application's development and its localization. There are four things you can do to resolve this contradiction.

**Run a pseudo-localized version of a program**

Pseudo-localization can be the most effective way of finding localizability bugs, which are generally detected when translating the program's UI. Pseudo-localization gives you a translation without the cost of an actual localization. (You can easily creating pseudo-localized versions using the [Multilingual App Toolkit](https://blogs.msdn.microsoft.com/matdev/).)

Once you pseudo-localize your program, test its functionality. Pseudo-localized applications should function no differently than their original version. Besides detecting localizability bugs, pseudo-localization often reveals globalization problems as well. As a result, testing a pseudo-localized application can potentially be central to verifying that an application is world-ready.

An area often forgotten in localizability testing is the pseudo-mirroring test, which can be implemented as part of the pseudo-localization of your product. If you want to distribute your software to markets where the text and UI of the programs display from right to left, you should follow the development and design rules outlined in "[Mirroring](https://msdn.microsoft.com/globalization/mt662335)" to allow mirroring of the UI. Pseudo-mirroring then verifies that these rules were applied. Testers do not need to wait for the localizers to mirror the UI of the application-pseudo-mirroring can be applied to the code. When conducting the pseudo-mirroring test, you can allow the UI text to remain unchanged and to be displayed as usual; only the windows and text alignment will be mirrored.

**Perform code review**

When reviewing your code, be sure it meets the following requirements:

-   All resources are separated from the code and are written in standard resources format. This does not mean you have to use Win32 resources only; the goal is to have them isolated from the code, easy to maintain and localize, and kept in a form that allows the application to access the proper language version of the resources.
-   Pointer arithmetic is not used for string-length calculations, access to string elements, or string manipulations. All text manipulations and parsing-such as finding string length, locating substrings, changing text case, and so on-have to be done using locale-sensitive and encoding-sensitive library routines.
-   Strings are not built at run time by stripping or concatenation. String substitution is done via language-aware APIs such as [FormatMessage](https://msdn.microsoft.com/en-us/library/windows/desktop/ms679351(v=vs.85).aspx).
-   Resource-handling mechanisms do not make assumptions about string buffer length. For example, if the application defines a name of a user with administrator's privileges and stores it as a string resource, it won't be a good idea to load it from a resource into a fixed buffer of 14 characters, just because the null-terminated string "Administrator" takes 14 characters. Since translation is likely to increase this length, the localized name might not fit into the buffer.
-   UI controls are not positioned at run time.
-   Icons and bitmaps do not contain text. Generally, try to make your graphics locale-neutral. Or, if they have to be locale-specific, the comment "localization required" must be attached and passed to the localizers.
-   No assumptions exist on drive and folder names or registry keys. The names of the system folders can be translated; the same can apply to the names of other objects defined by the operating system and applications your code interacts with. Folder names, names of built-in accounts, and other localizable elements of the operating system can and should be queried at run time. If your application defines localizable objects of this kind, make sure they can be changed with no modifications to the code. For example, if an installation routine creates folders with localizable names, make sure that code working with those folders can find them using the same localizable resource or some language-neutral mechanism like an environment variable.

**Perform UI and documentation review**

Ensure the terminology used in the UI and support documentation is clear, consistent, and unambiguous. Localizers find it hard to do their jobs when the UI and the documentation refer to the same features but use different words, or when the text is overloaded with technical slang. Content review becomes even more important if your localizability relies on pseudo-localization. Pseudo-localization helps to find code problems; automatic machine methods cannot find language that is too technical, unclear, or inconsistent with that used in other parts of the documentation.

**Run a pilot localization project**

Though there are many advantages to pseudo-localizing your application, you might opt to run an actual pilot localization project (such as if you are localizing for only a couple of European languages or if you cannot afford to build a pseudo-localized version of a product). If you choose this method, first, you should use one language for which you can easily organize localization and testing. For instance, maybe you have experience with this particular language from your previous projects, or your organization employs people who speak this language.

Second, you should choose a language for which the localization is especially likely to expose localization problems. German can be a good example because the translated text is likely to grow in length. For example, "cut (and paste)" translates as "ausschneiden (und einfügen)" in German.

Third, choose a language for which the target market of the localized product is of great importance to you. The pilot language version will be the first product that is ready for shipping.

In spite of its benefits, pilot localization cannot guarantee that all issues will be covered in your localizability test. Different language versions might vary in the degree of translation required and in the problems you are likely to see due to localization. By using pseudo-localization to address general areas of potential risk, you will preempt more problems than by using pilot localization, which focuses more on the requirements dictated by one particular language.


