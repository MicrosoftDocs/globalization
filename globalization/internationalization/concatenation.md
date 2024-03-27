---
title: String concatenation
description: Discover alternatives to string concatenation that give translators more control over words, order, punctuation, and spacing.
ms.date: 3/26/2024
author: jowilco
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-desc
  - ai-seo-date:03/26/2024
---

# String concatenation

Concatenated strings are one of the most challenging issues for translators to resolve during translation. In some cases, translators won't be able to provide appropriate translations such that a meaningful string is generated once the fragments have been concatenated. This article reviews some of the most common issues with string concatenation and localization.

For this article, we use an example string from an e-commerce application: ```You have 5 items in your shopping cart.```

In English, to ensure grammatical correctness, you might want to display different strings for one item: ```You have 1 item in your shopping cart.```

One way of implementing this string is three separate fragments:

```text
YouHave = "You have"
Item = "item"
InYourShoppingCart = "in your shopping cart"
```

You could then generate the final string as:

```text
myString1 = String.Format(YouHave + " 1 "+ Item + " " InYourShoppingCart" + ".")
myStringOther = String.Format(YouHave + " " + {0} + " "+ Item + "s " InYourShoppingCart" + ".", myItems)
```

There are several issues with this approach.

## Fragments out of order

Your resource file format might not guarantee the order of the strings in the file. For example, if your development environment sorts the strings via resource identifier, you might get something like:

```text
…
InYourShoppingCart = "in your shopping cart"
…
Item = "item"
…
YouHave = "You have"
…
```

It would be difficult for translators to understand how to translate "You have" or "in your shopping cart" without any idea how these string fragments will be used.

## Pluralization

In ```myStringOther``` "s" is being appended (concatenated) to "item" to generate "items" for any value that isn't 1. Creating plurals by adding an s works for many nouns in English. For other languages, this causes issues:

- Languages don’t create plurals by appending "s". For example, in Italian, "1 item" = "1 articolo", "2 items" = "2 articoli"
- Languages don’t change the noun as the number of objects change. For example, in Japanese, "1 item" = "1 個の商品", "2 items" = "2 個の商品"
- Languages have more than two forms for plurals. For example, in Russian, "1 item" = "1 товар", "2 items" = "2 товара", "5 items" = "5 товаров"

For more information about handling plurals in text, see [Pluralization](pluralization.md)

## Punctuation marks

In both myString1 and myStringOther, the string ends with a period (U+002E FULL STOP). While ending a sentence with a period is common in languages that use the Latin script, other languages use alternatives. For example, Japanese uses 。 (U+3002 IDEOGRAPHIC FULL STOP) while Thai doesn’t consistently use a punctuation mark to separate sentences.

Languages using the same script might use different punctuation marks. For example, English uses quotation marks (for example, U+0022 QUOTATION MARK) while French uses guillemets « » (U+00AB LEFT-POINTING DOUBLE ANGLE QUOTATION MARK, U+00BB RIGHT-POINTING DOUBLE ANGLE QUOTATION MARK) to indicate quoted text. English uses the ? (U+003F QUESTION MARK) to indicate the end of an interrogative sentence while Spanish adds the ¿ (U+00BF INVERTED QUESTION MARK) at the start of the interrogative clause.

Even when different languages use the same punctuation marks, the rules around usage might be different. French uses spaces to separate many punctuation marks from text. For example, French adds a space before and after the quoted text and the guillemets, as well as spaces before question marks.

By including all punctuation marks in translatable content, translators have full control of the characters used for punctuation and of ensuring compliance with punctuation usage rules.

## Word separation

In both myString1 and myStringOther, spaces have been added to separate the fragments/words. Separating words using spaces is common in several scripts; other languages use different separator characters or don’t separate words. For example, Chinese doesn't use word separators, and the Ge’ez script has the ፡ (U+1361 ETHIOPIC WORDSPACE).

## Sentence structure

English typically follows a subject-verb-object structure. In our example, "You" is the subject, "have" is the verb, and "item in your shopping cart" is the object.

Other languages use different structures. For example, Japanese uses subject-object-verb:

- ショッピングカートには 5 個の商品が入っています。
- (You) shopping cart in 5 items have.

If you compare this order to the original string fragments, it would be difficult to translate the string fragments such that the concatenation would result in the correct output.

## Alternatives to concatenation

One solution for this example, which avoids many of the issues mentioned, is:

```text
myString = "Items in the shopping cart: {0}"
```

While this version of the string might not be as elegant, the translators have full control over the words, the word order, punctuation, and spacing. The structure also mitigates issues with pluralization based on the number of items.

## Other common concatenation issues

In addition to the issues highlighted in the example, several other issues are common with string concatenation and localization.

### Sentence separation

In English, comparable to word separation, sentences are also separated with spaces. You shouldn't assume that this is true for all scripts and languages.

Use a single string to contain multiple sentences, rather than having a separate string for each sentence then concatenating the strings.

### Variable order

You shouldn't assume that variables in a string will be used in the same order in other languages. As mentioned previously, sentence structure varies by language, so the order of the variables might need to change depending on the sentence structure.

A simple example to illustrate this issue is names. In English, the given name (first name) appears before the family name (surname). In Japanese, the family name appears before the given name.

### Adjective and noun agreement

In English, adjectives generally don’t change as the noun changes. For example, "**blue** bicycle", "**blue** car". In French, the adjective appears after the noun and changes depending on the gender of the noun. For example, "vélo **bleu**", "voiture **bleue**".

While it might be tempting to concatenate adjectives and nouns, or even use variables to generate strings that combine adjectives and nouns, gender agreement can make this very challenging to implement correctly in other languages.

## Testing for concatenation

As concatenation is such a significant issue for localization, using [pseudolocalization](../methodology/pseudolocalization.md) testing before starting translation can reduce costs and rework. Let’s look at two examples of strings and how they might appear when pseudolocalized.

```text
Example 1
String_part1 = "You have "
String_part2 = " items in your shopping cart."

Example 2
String = "You have {items} items in your shopping cart."
```

When pseudolocalized, these strings might result in the following sentences in the UI.

```text
Example 1
[!!!You have !!!]5[!!! items in your shopping cart.!!!]

Example 2
[!!!You have 5 items in your shopping cart.!!!]
```

You can see the sentence fragments surrounded by [!!! and !!!] in the first (concatenated) example, while the complete sentence is surrounded in the second example.
