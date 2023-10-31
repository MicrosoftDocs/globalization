---
title: Writing systems, scripts, and languages
description: A writing system uses a defined set of symbols or characters, and a set of rules (orthography) to represent a language.
ms.date: 10/31/2023
author: jowilco
---

# Writing systems, scripts, and languages

Language is a form of communication that relies on words (vocabulary) and rules for using the words (grammar). A *writing system* uses a defined set of symbols or characters, and a set of rules (orthography) to represent a language. The set of characters used by a given writing system is called a *script*. English uses a single script (Latin), while Japanese is written using four scripts (Kanji, Hiragana, Katakana, and Latin (romaji)).

## Types of writing systems

There are various approaches to categorize writing systems, all of which have limitations as writing systems can have features of more than one category. In our previous example, Japanese uses a combination of logographic (Kanji), syllabic (Hiragana, Katakana), and alphabetic (Romaji) systems. However, having a general idea of the different types of writing systems will help to understand topics like [text layout](text-layout.md), [text boundaries](text-boundaries.md), and [pagination](pagination.md).

### Pictographic and ideographic

A pictograph is a symbol that conveys a meaning through a resemblance to a physical object. Some emojis are pictographs. For example, a smiling face emoji (e.g., U+263A) can represent the concept of happiness.

An ideograph is a symbol that does not resemble a physical object, but still conveys a specific meaning independent of language. Numerals and mathematical symbols are examples of ideographs.

### Logographic

A logograph is a character that represents a word or a morpheme (the smallest unit of a language that has a distinct meaning). Chinese characters are examples of logographs.

### Syllabic

In a syllabic writing system, each character represents a syllable or a mora (a unit equivalent to a short spoken syllable). Cherokee language is typically written using the Cherokee syllabary, while hiragana and katakana in Japanese are examples of moras. To illustrate the difference between a syllable and a mora, the word Japan (日本) in Japanese can be pronounced as “nihon”. The second syllable (hon) is represented using two moras (ほん) in hiragana.

### Abugida (syllabic alphabet)

An abugida (named after the first 4 letters of the Ge'ez script) is like a syllabic writing system in that each character represents a syllable. However, syllabic writing systems have different characters for every syllable, whereas characters in an abugida have common characteristics for similar syllables. Typically, the characters are based on the consonants, and a vowel sign is added to the consonant to modify the sound. Devanagari, used to write Hindi and other languages, is an example of an abugida.

Even within a single script, the vowel sign can occur to the right, to the left, above, or below the consonant. In some abugidas, multiple consonants (consonant clusters) can be combined, also known as stacking. Stacking can occur across word and syllable boundaries, and stacks are not split when [breaking lines](line-and-word-breaking.md). In other words, line breaking occurs at the boundaries of “orthographic syllables” rather than “phonetic syllables”.

### Alphabet

An alphabet (named after the first 2 letters of Greek) has distinct characters (letters) for consonants and vowels. Alphabets differ from abugidas and abjads as characters are used for each vowel rather than vowels modifying the character for the consonant (abugidas) or rather than vowels being omitted (abjads). Combinations of letters represent phonemes in the spoken language, however:

- the same combination of letters might represent different phonemes: in English, “ough” has several pronunciations, including /ʌf/, /ɒf/, and /ɔː/
- the same phoneme can be represented using different combinations of letters: in English, /aʊ/ can be spelled as o, ou, or ow.

### Abjad (consonant alphabet)

An abjad (named after the first 4 letter of Semitic languages) has characters for consonants. In some abjads, vowels can be indicated with the use of diacritical marks. Arabic and Hebrew are examples of abjads.

### Featural

Hangul, the modern writing system for the Korean language, is an example of a featural writing system. Korean is written in syllabic blocks, with jamo (consonants and vowels) combined from left-to-right and top-to-bottom.

## Directionality

Another way of categorizing writing systems is by the direction in which the script is typically written. Latin scripts are written from left-to-right. Arabic is written from right-to-left. Chinese and Japanese can be written either horizontally from left-to-right from the top to the bottom of the page and vertically from top-to-bottom from the right to the left of the page. See [Pagination and text alignment](pagination.md) for more details.
