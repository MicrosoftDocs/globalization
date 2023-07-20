---
title: Polish Localization Style Guide
description: Are you helping with translation into Polish, but don't have time to study all of the Polish Style Guide? Here are the ten most important aspects.
ms.date: 04/18/2019
---
# Top 10 Tips for Microsoft Translation into Polish

Are you helping with translation into Polish, but don't have time to study all aspects of the [full Polish Style Guide](../../reference/microsoft-style-guides.md)? Here are 10 of the most important aspects to keep in mind.

## 1. Flexibility

It's important for translators to modify or rewrite translated strings so that they are more appropriate and natural to Polish customers. Try to understand the whole intention of the sentences, paragraphs, and pages, and then rewrite as if you are writing the content yourself. Sometimes, you may need to remove any unnecessary content.

Example:

_English_: Prioritizing your social updates is just another way Messenger helps you keep connected with the people who matter most.

_Our style_: <span lang="pl">Messenger dba o Twoje relacje z najbliższymi osobami, pokazując aktualności
społecznościowe w widocznym miejscu.</span>

_Not our style_: :::no-loc text="Priorytetyzacja aktualizacji społecznościowych jest po prostu innym sposobem, w jaki Messenger pomaga zachować łączność z osobami, które mają największe znaczenie.":::

## 2. Word-for-word translation

For a more fluent translation, avoid word-for-word translation. If words are translated directly without an overall understanding of the paragraph or page, the content will sound stiff and unnatural. Split the text into different sentences, if necessary, to simplify.

Example:

_English_: Use this feature to achieve your goals.

_Our style_: :::no-loc text="Dzięki tej funkcji osiągniesz zamierzone cele.":::

_Not our style_: :::no-loc text="Użyj tej funkcji do osiągnięcia swoich celów.":::

## 3. Terminology

Product and application names are often trademarked or may be trademarked in the future. These names, therefore, are rarely translated. Occasionally, feature names are trademarked, too. Before translating any application, product, or feature name, verify that it's in fact translatable and not protected in any way. That information can be obtained from the [Microsoft trademarks list](https://www.microsoft.com/legal/intellectualproperty/trademarks/en-us.aspx).

## 4. Capitalization

Don't copy the capitalization of the English source text. In English, it's a general practice to capitalize the first characters of the words in titles, names, and headings, and sometimes the middle characters in words, too. Bear in mind that this capitalization is an error in Polish text.

In English, the days of the week, the names of months, and language names are also capitalized. In Polish they aren't capitalized. In titles and the names of programs, dialog boxes, check boxes, and similar places, only the first word is capitalized, unlike in English.
Some products use a very specific capitalization style. For example, they use ALL CAPS or all lowercase for the names of user interface parts. In such cases the specific style should be preserved in the translation to follow the original marketing design, and the Polish translation should follow the source for ALL CAPS and all lowercase styles.

Example:

_English_: Try Again

_Our style_: :::no-loc text="Spróbuj ponownie":::

_Not our style_: :::no-loc text="Spróbuj Ponownie":::

## 5. Gender

When translating English text, you have to remember that many different kinds of people use our products. It's important to choose vocabulary and select verbs that are gender neutral and inclusive.

Example:

_English_: Forgot your password?

_Our style_: :::no-loc text="Nie pamiętasz hasła?":::

_Not our style_: :::no-loc text="Zapomniałeś hasła?":::

## 6. Modifiers

In localized Polish text you often need to precede terms, especially if they are left in English, by the respective modifier. One of the most common errors is omitting a modifier before the names of products, objects, and so on, or trying to inflect the English name with the Polish ending.

In Polish localized text you always need to add the modifier before the name of the object, menu, command, dialog box element, icon, or similar element.

Example:

_English_: All Word commands

_Our style_: :::no-loc text="Wszystkie polecenia programu Word":::

_Not our style_: :::no-loc text="Wszystkie polecenia Worda":::

## 7. Possessive adjectives and pronouns

The frequent use of possessives is a feature of the English language. The common use of possessive adjectives in English should be avoided in Polish.

In Polish, the use of pronouns is limited. Although the actual translation depends on the source text, the general rules are:

- Pronouns are used less frequently in Polish than in English. If the meaning of the sentence doesn't require the use of the pronoun in the localized text, it's better to skip the pronoun. Don't overuse pronouns. Too many pronouns may make the text sound unnatural.
- First-person singular forms are preferred when the user is telling the program or a wizard what to do.
- First-person plural forms are preferred when the Microsoft product or service is addressing the user.
- Second-person forms (which address the user directly) are preferred when the program or a wizard is telling the user what to do.
- Third-person references ("user") should be avoided.

Personal and possessive pronouns referring to the user (_:::no-loc text="Ty, Twój, Twojego":::_, and so on) should always start with a capital letter.

Example:

_English_: This program cannot be run on your computer.

_Our style_: :::no-loc text="Programu nie można uruchomić na tym komputerze.":::

_Not our style_: :::no-loc text="Tego programu nie można uruchomić na Twoim komputerze.":::

## 8. Dashes and hyphens

Three different dash characters are used in Polish.

The hyphen (&hyphen;) is used to divide words between syllables, to link parts of a compound word, and to connect the parts of an inverted or imperative verb form.

Example:

_Our style_:

- :::no-loc text="Bielsko-Biała":::
- :::no-loc text="w DOS-ie":::
- :::no-loc text="30-procentowy":::
- :::no-loc text="16- i 32-bitowe":::

The en-dash (&ndash;) is used as a minus sign, usually with spaces before and after. It's also used in number ranges, such as those specifying page numbers. No spaces are used around the en-dash in this case.

Example:

_Our style_:

- :::no-loc text="ZAROBKI – WYDATKI = 2 000 000":::
- :::no-loc text="Opis ten podano na ss. 236–238":::
- :::no-loc text="w latach 1989–1991":::

The em dash (&mdash;) should be used only to emphasize an isolated element or introduce an element that's not essential to the meaning conveyed by the sentence.

Example:

_Our style_: :::no-loc text="Microsoft Excel — Pomoc":::

## 9. Quotation marks

Quotation marks are used when referring to quoted text. The correct Polish quotation marks are lower-upper („ ").
In English, when the text between quotation marks appears at the end of the sentence, the period may appear inside the quotation marks. In Polish, the period should go outside the quotation marks. Even if the whole sentence is between quotation marks, the period goes outside.

Example:

_English_: Field "{0}" is required

_Our style_: :::no-loc text="Pole „{0}" jest wymagane":::

_Not our style_: :::no-loc text="Pole "{0}" jest wymagane":::

## 10. Recommended normative references

Use the Polish language and terminology as described and used in the following normative references.

Before adopting a new term, make sure an equivalent term doesn't already exist. Verify the spelling and hyphenation of new terms. Check Polish language dictionaries, Microsoft product glossaries and reference materials, competitive products' documentation and websites, and standards organizations such as the [Polski Komitet Normalizacyjny](https://pkn.pl/) (Polish committee for standardization or PKN).

1. :::no-loc text="Słownik poprawnej polszczyzny":::, PWN, the latest edition
2. :::no-loc text="Słownik języka polskiego":::, PWN, the latest edition
3. :::no-loc text="Nowy słownik ortograficzny języka polskiego":::, PWN, the latest edition
