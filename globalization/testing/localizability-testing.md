---
title: Testing localizability
description: Localizability testing verifies if the user interface of the program can be translated to any target language without code modifications.
---

# Testing localizability

The purpose of localizability testing is to verify that the user interface of the program being tested can be easily translated to any target language without re-engineering or making code modifications.
Since localizability bugs must be fixed in the code of the application, they must be looked for at the earliest stage of development possible.
By doing so, you can circumvent having to discover and fix bugs for each target language at a later point.

Paradoxically, the problems that cause bugs to appear often become apparent only once localization is done.
Localization is expensive, so it often occurs only after the code is complete and reaches a certain degree of stability. There is inevitably a gap between an application's development and its localization.

There are four things you can do to resolve this contradiction.

1. [Review code](#review)
2. [Run a pseudolocalized version of the application](#pseudo)
3. [Run a pilot localization](#pilot)
4. [Review UI and documentation](#review-ui-docs)

## <a name="review"></a>Review code

When reviewing your code, be sure it meets the following requirements:

* Localizable resources are separated from the code and defined in a localizable resource format.

* Pointer arithmetic is not used for string-length calculations, access to string elements, or string manipulations.
  All text manipulations and parsing-such as finding string length, locating substrings, changing text case, and so on-have to be done using locale-sensitive and encoding-sensitive library routines.

* Verify that strings are not built at run time by stripping or concatenation.
  Be sure that string substitution is done via language-aware methods.

* Resource-handling mechanisms do not make assumptions about string buffer length.

  For example, if the application defines a name of a user with administrator's privileges and stores it as a string resource, it won't be a good idea to load it into a fixed buffer of 14 characters, just because the null-terminated string "Administrator" takes 14 characters.
  Translation will often increase this length, so the translated name might not fit into the buffer.

* If not using adaptive UI, do not position UI controls at run time.

* Icons and bitmaps do not contain text.
  Generally, try to make your graphics locale-neutral. Or, if they have to be locale-specific, the comment "localization required" must be attached and passed to the localizers.

* No assumptions exist on folder names or registry keys.
  The names of the system and special folders can be translated.
  The same can apply to the names of other objects defined by the operating system and applications your code interacts with.
  The names of special folders, the names of built-in accounts, and other localizable elements of the operating system can and should be queried at run time.
  If your application defines localizable objects of this kind, make sure they can be changed with no modifications to the code.
  For example, if installation creates folders with localizable names, make sure that code working with those folders can find them using the same localizable resource or some language-neutral mechanism.

## <a name="pseudo"></a>Run a pseudolocalized version of the application

Pseudolocalization (informally, "pseudo") can be the most effective way of finding localizability bugs, which are otherwise only detected when translating the application.
Pseudolocalization gives you a "translation" without the cost of an actual translation.
You can create pseudolocalized resources using the [Multilingual App Toolkit](/windows/uwp/design/globalizing/use-mat), or other translation tools.

See [Pseudolocalization](../methodology/pseudolocalization.md) for general information on pseudo.

Once you pseudolocalize your application, test its functionality.
Pseudolocalized applications should function no differently than their un-localized version.
Besides detecting localizability bugs, pseudolocalization often reveals globalization problems as well.
As a result, testing a pseudolocalized application can potentially be central to verifying that an application is world-ready.

An area often forgotten in localizability testing is the pseudo-mirroring test, which can be implemented as part of pseudo-localization.
If you want to distribute your software to markets where the text and user interface of the programs display from right to left, you should follow the development and design rules outlined in [User interface layout](../localization/layout.md) to allow mirroring of the UI.
Pseudo-mirroring then verifies that these rules were applied.
Testers do not need to wait for the localizers to mirror the UI of the application: pseudo-mirroring can be applied to the code.
When conducting the pseudo-mirroring test, you can allow the UI text to remain unchanged and to be displayed as usual; only the windows and text alignment will be mirrored.

## <a name="pilot"></a>Run a pilot localization

There are many advantages to pseudolocalizing your application, but it can never catch all the issues.
You might opt to run an actual pilot localization project before taking on the full list of languages.
A pilot can be done instead of pseudolocalization, but it is best to do both.

If you choose to run pilot localization, choose one or two languages for which you can easily organize localization and testing.
For instance, maybe you have experience with the language from previous projects, or your organization employs people who speak the language.

Choose languages for which the localization is especially likely to expose localization problems.
German can be a good example because the translated text is likely to grow in length, and there are particular characteristics to the writing conventions and regional formats.
For an example of string expansion, "cut and paste" (13 characters) translates as "ausschneiden und einfügen" (25 characters) in German—nearly twice as long (and contains a diacritic).

Choose a language for which the target market of the localized product is of great importance to you.
The pilot language version will be the first that is ready to ship.

In spite of their benefits, pseudo and pilot localization cannot guarantee that all issues will be covered in your localizability test.
Every language is different.
A given language might vary in the degree of translation required and in the problems you are likely to see due to localization.
Pseudolocalization addresses general areas of potential risk, and you will preempt more problems than by using pilot localization alone.
A pilot localization will naturally focus more on the requirements dictated by that particular language.

## <a name="review-ui-docs"></a>Review UI and documentation

Ensure the terminology used in the user interface and support documentation is clear, consistent, and unambiguous.
Localizers find it hard to do their jobs when the UI and the documentation refer to the same features but use different words, or when the text is overloaded with technical slang.
Content review becomes even more important if your localizability relies on pseudo-localization.
Pseudolocalization works well to find code, string handling, and layout problems in the application, but is less effective for documentation.
Automatic machine methods cannot find language that is too technical, unclear, or inconsistent with that used in other parts of the documentation.
