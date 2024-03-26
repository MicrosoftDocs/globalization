---
title: Pluralization
description: Forming plurals varies widely in different world languages, and software must take the local language into account when combining text and numbers.
ms.date: 3/26/2024
author: jowilco
---

# Pluralization

In linguistics, *grammatical number* is how nouns, pronouns, adjectives, and verb agreements are modified based on the quantities of objects. As discussed in [Message formatting](message-formatting.md), handling quantities of nouns can be challenging. English, and many other languages, have a contrast between singular and plural. Other languages have more elaborate systems of grammatical numbering.

You can attempt to avoid pluralization issues using constructions like:

```text
You have {count} apple(s).
Apples in your shopping cart: {count}
```

Both examples avoid using separate strings for different values of {count}. However, it results in constructions that do not sound natural. To implement the first example to sound more natural in English, you might need two separate strings to handle the singular and plural forms:

```text
mystring_singular = You have 1 apple.
mystring_plural = You have {count} apples.
```

However, just having a string when {count} is 1 and a string for when {count} is any other value is not sufficient to support other languages. For example, in French, both 0 and 1 are considered singular. Russian uses different forms depending on whether you have one (1 яблоко), a few (2 яблока), or many (5 яблок) objects.

[International Components for Unicode](..\reference\icu.md) (ICU) enables support for [plural rules](https://cldr.unicode.org/index/cldr-spec/plural-rules) to handle the various forms of plural categories. The plural rules cannot cover all the nuances of representing numbers in languages; however, ICU supports the following plural categories (forms) to handle many cases:

- zero
- one (*singular*)
- two (*dual*)
- few (*paucal*)
- many
- other

The **other** form is always required, and so is used for languages that only have a single form. Note that other categorizations exist, such as *trial* (three), and *quadral* (four), and *superplural* (larger than plural). ICU also specifies how each language uses these forms ([Language Plural Rules](https://www.unicode.org/cldr/charts/latest/supplemental/language_plural_rules.html)).

## Cardinal Pluralization

The following example shows how to use plural rules to display natural sounding text in English, French, and Polish, to represent a count of articles that have been read. The example uses [Globalize.js](https://github.com/globalizejs).

```nodejs
var Globalize = require("globalize");
Globalize.load(require("cldr-data").entireSupplemental());
Globalize.load(require("cldr-data").entireMainFor("en", "fr", "pl"));

Globalize.loadMessages({
    en: {
        articles: [
            "{cardinal, select, ",
            "zero  {You have read {formattedCount} articles.}",
            "one   {You have read {formattedCount} article.}",
            "two   {You have read {formattedCount} articles.}",
            "few   {You have read {formattedCount} articles.}",
            "many  {You have read {formattedCount} articles.}",
            "other {You have read {formattedCount} articles.}",
            "}"
        ]
    },
    fr: {
        articles: [
            "{cardinal, select, ",
            "zero  {**Not used**}",
            "one   {Vous avez lu {formattedCount} article.}",
            "two   {**Not used**}",
            "few   {**Not used**}",
            "many  {**Not used**}",
            "other {Vous avez lu {formattedCount} articles.}",
            "}"
        ]
    },
    pl: {
        articles: [
            "{cardinal, select, ",
            "zero  {**Not used**}",
            "one   {Przeczytałeś {formattedCount} artykuł.}",
            "two   {**Not used**}",
            "few   {Przeczytałeś {formattedCount} artykuły.}",
            "many  {Przeczytałeś {formattedCount} artykułów.}",
            "other {Przeczytałeś {formattedCount} artykułu.}",
            "}"
        ]
    },

});

const locales = ["en", "fr", "pl"];
const values = [0, 1, 1.5, 2, 5];
for (let i = 0; i < locales.length; i++) {
    var numberFormatter = Globalize(locales[i]).numberFormatter();
    var cardinalGenerator = Globalize(locales[i]).pluralGenerator({ type: "cardinal" });
    var articlesFormatter = Globalize(locales[i]).messageFormatter("articles");
    for (let j = 0; j < values.length; j++) {
        console.log(
            articlesFormatter({
                cardinal: cardinalGenerator(values[j]),
                formattedCount: numberFormatter(values[j])
            })
        );
    }
}
```

Output:

```text
You have read 0 articles.
You have read 1 article.
You have read 1.5 articles.
You have read 2 articles.
You have read 5 articles.
Vous avez lu 0 article.
Vous avez lu 1 article.
Vous avez lu 1,5 article.
Vous avez lu 2 articles.
Vous avez lu 5 articles.
Przeczytałeś 0 artykułów.
Przeczytałeś 1 artykuł.
Przeczytałeś 1,5 artykułu.
Przeczytałeś 2 artykuły.
Przeczytałeś 5 artykułów.
```

In English, sentences for all 6 forms have been included. This is best practice, even if other languages don’t use all the forms.

## Ordinal pluralization

Languages might have different pluralization rules for ordinal and cardinal numbers. For example, in English there are only two forms for cardinal numbers (singular and plural), but ordinal numbers have 4 forms:

- one: 1st
- two: 2nd
- few: 3rd
- other: 4th, 5th, 10th, 100th.

This example shows an implementation showing the generation of English and French ordinal numbers:

```nodejs
var Globalize = require("globalize");
Globalize.load(require("cldr-data").entireSupplemental());
Globalize.load(require("cldr-data").entireMainFor("en", "fr"));

Globalize.loadMessages({
    en: {
        articles: [
            "{ordinal, select, ",
            "zero  {This is the {count}th article.}",
            "one   {This is the {count}st article.}",
            "two   {This is the {count}nd article.}",
            "few   {This is the {count}rd article.}",
            "many  {This is the {count}th article.}",
            "other {This is the {count}th article.}",
            "}"
        ]
    },
    fr: {
        articles: [
            "{ordinal, select, ",
            "zero  {**Not used**}",
            "one   {Ceci est le {count}er article.}",
            "two   {**Not used**}",
            "few   {**Not used**}",
            "many  {**Not used**}",
            "other {Ceci est le {count}ème article.}",
            "}"
        ]
    }

});

const locales = ["en", "fr"];
const values = [1, 2, 3, 4, 23];
for (let i = 0; i < locales.length; i++) {
    var articlesFormatter = Globalize(locales[i]).messageFormatter("articles");
    var ordinalGenerator = Globalize(locales[i]).pluralGenerator({ type: "ordinal" });
    for (let j = 0; j < values.length; j++) {
        console.log(
            articlesFormatter({
                count: values[j],
                ordinal: ordinalGenerator(values[j])
            })
        );
    }
}
```

Output:

```text
This is the 1st article.
This is the 2nd article.
This is the 3rd article.
This is the 4th article.
This is the 23rd article.
Ceci est le 1er article.
Ceci est le 2ème article.
Ceci est le 3ème article.
Ceci est le 4ème article.
Ceci est le 23ème article.
```
