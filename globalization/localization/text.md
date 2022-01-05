---
title: Text translation
description: Text translation is the most important aspect of localizing the software UI.
---
# Text translation

Text translation is the most important aspect of localizing software.
The translation should communicate in language, phrasing, and vocabulary that is natural as well as accurate.
The language should be clear, familiar to the user, and appropriate for the culture of the target country.
Additionally, it should follow conventions used in the target country such as customary symbols, punctuation, formatting, and typography.
Title bars, menus, dialog boxes, buttons, messages, and tool tips are some common user interface controls that have text.
Help files and user manuals typically require heavy translation efforts.

Translation does not always result in a one-to-one correspondence between the source and target language.
A single word in English can have multiple translations in another language, depending on context.
For instance, the word "supply" in English can have varying translations in Spanish, depending on whether the word is used as a verb or as a noun.
Even within the verb and noun categories themselves, the Spanish translation can differ depending on the particular context.
On the other hand, certain English words might have only a single meaning in another language.
In addition to semantic variations among words from one language to another, adjectives and articles sometimes change spelling according to the gender of the nouns.
This becomes especially problematic when a noun is interpolated into a string at run-time.
Therefore, when re-using a text string in multiple places, localizers need to make sure that the string is translated in such a way that the text is correct for a given context.
(For more information, see [String Handling](../localizability/string-handling.md).)

Consistent and precise terminology throughout the software application helps the user to learn the application faster and makes the translation time shorter.
For example, "traveling" and "travelling" are both correct in English, but it is better to use only one variation of the word in the product.
Localizers should do the same for the localized text.
Having consistent terminology in the original-language product is particularly important if the localization team uses automatic translation tools because the tool might not translate the variation in the same way.
Consistent and clear phrasing of the original text makes localization easier and prevents confusion for localizers, who might interpret the text differently from what was meant.
Localizers should avoid "sublocale" idioms, colloquialisms, or metaphors, since these might be meaningless - or even offensive - among cultures that use the same language.

Some locales share the same language yet use different words for the same object.
For instance, the word "computer" is "ordenador" in Spain and "computador" in Mexico and Puerto Rico (both of which are masculine in gender).
The word "computadora" is used in the rest of Latin America (and the word's gender changes from masculine to feminine).
To resolve such issues, if there is one translation that is considered acceptable for all locales, localizers should use this particular wording.

In general, the text (as well as the graphics and other elements) of the localized software product should not be altered to reflect locale-specific geopolitical views because this could cause inconsistency in the localized product.
Nonetheless, sometimes there could be undesirable consequences resulting from a localized product that is not adapted to meet a locale's geopolitical views.
If the views conveyed in the unaltered product are going to offend the target market, this will affect sales in that market or have legal consequences.
Such a situation would warrant alteration of the localized product.
For disputes over national borders, maps, country names, international or political organizations and leaders, or any other politically sensitive subjects, consult an expert on geopolitical issues for advice.
Then make any necessary adjustments in the original product.
For more information on political content, see [Localizability Overview](../localizability/overview.md).
