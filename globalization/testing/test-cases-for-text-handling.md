---
title: Test cases for text handling
description: Globalization test cases for handling text.
ms.assetid: 3261e61f-09a9-476d-b5ae-38a8fafebfcc
ms.date: 04/14/2017
---

# Test cases for text handling

This article contains some sample test cases for text handling.

## Interactive text input using different input locales

Enter text while switching between different keyboard layouts and Input Method Editors (IMEs).
Verify the ability of the application to accept input from various input methods, regardless of other locale settings.
Either check that multilingual input is enabled with all supported input methods or that it's blocked for all languages except supported ones.

**Applicability:** Applications that allow for interactive text input

## Clipboard operations with multilingual text

Verify that multilingual text can be copied to and from the clipboard.
Make sure the use of the clipboard while cutting and pasting does not compromise the limitations placed on localized text.
Examples of such limitations might be those imposed on applications interacting with non-multilingual components or systems, or when the text being passed on must match the system locale.

**Applicability:** Applications that allow clipboard operations.

## Device-independent multilingual output

All methods of output-such as displaying UI text, printing, storing in an enhanced metafile (EMF)-must preserve the multilingual features of the text.
These methods should not introduce problems due to different text encoding, font, or settings used for other output methods.

**Applicability:** Applications that perform text output.

## Font independence

Verify that the names of fonts the application uses are not hard-coded.
Run the application on a localized operating system where font names are localized and where default shell fonts are different from those used in the English operating system.
Localized Japanese Windows is a good example.
Change the default font settings of the applications.

**Applicability:** Applications that have text in the UI.

## Text handling in the UI

Check that multilingual text can be edited, entered, and deleted. Verify that word wrapping breaks text properly, regardless of the language.
Make sure characters can be changed to uppercase and lowercase according to the settings of the language and the locale.
Verify alignment of the multilingual output.

**Applicability:** All applications that perform special text formatting; applications that use custom solutions, rather than standard Windows controls, for text editing.

## Cursor movement and positioning

Verify that the cursor can be positioned correctly at the start and end of characters and text. Check cursor movement and text selection.
Pay greater attention to wide ideographic characters (such as kanji characters) and bidirectional (bidi) text, since these can cause cursor movement problems if not handled properly.

**Applicability:** Applications that don't use standard Windows controls for text editing.

## Handling of double byte character sets (DBCS)

Set an East Asian system locale; use text encoded with single-byte and double-byte values in the selected code page. Incorporate into the test data characters that might be "risky" for your application.

**Applicability:** Applications that implement non-Unicode text handling.

## Handling of OEM and Windows encodings

Set the system locale where some character code-point values defined by Windows and OEM code pages are different.
For example, the code-point value of "small sharp s" (ß) is 0xE1 in code page 850, set with the German system locale.
However, Windows code page 1252, which is associated with this same German system locale, defines this letter as 0xDF.
Use characters such as ß in the test data, and verify that they are never displayed, stored, or retrieved as some other character.

**Applicability:** Applications that implement non-Unicode text handling; network and console applications.

## Complex script handling

Multilingual applications must process complex scripts correctly-either by using standard Windows controls or calling special complex-script handling routines like those of Uniscribe.
Check that bidi text is properly reordered, that Arabic text is correctly shaped, and that word-breaking rules are applied to Thai text.

**Applicability:** Applications that implement custom complex-script handling; basic verification is required for all applications sold in markets where complex scripts are used.

## Handling buffer sizes for multi-byte character set (MBCS) text

Make sure that text conversions between encodings that use different numbers of bytes per character do not cause buffer overflows, memory leaks, or text truncations.
Storage of the same text encoded in UTF-16, UTF-8, and UTF-32, might require buffers of different sizes.

**Applicability:** Applications that handle different text encodings.

## Language-independent data persistence

Applications must store and retrieve data containing multilingual data, regardless of the language settings of the system where the operation is performed.

**Applicability:** All applications that store data in persistent storage.
