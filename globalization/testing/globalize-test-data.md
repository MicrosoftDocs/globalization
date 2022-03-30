---
title: Globalize test data
description: Test data should be multilingual Unicode text different from the system locale. Use mixed scripts or Unicode-only text to discover codepage dependencies.
---

# Globalize test data

After the environment has been set for globalized testing, your regular test cases must be run with special attention paid to potential globalization problems.
The test data must match the test.
Use a mix of scripts such as Latin, Cyrillic, Armenian, Georgian, Thai, and Indic languages.

Some particular areas of functionality might require special test data.

## Letter case

If the application converts the case of text, you can verify the functionality with scripts that do not have uppercase and lowercase symbols, such as Cyrillic, East Asian scripts, and Hebrew.

You can also use text where there are locale-specific rules for case conversion, such as Turkish.
Turkish uses upper and lower case, dotted and dotless letter "I".
Unlike other languages written in the Latin script, Turkish "I"s do not gain or lose their dots when changing case.

| Code point | Unicode Character Name                | Letter                    | Opposite case (Turkish) |
|------------|---------------------------------------|---------------------------|-------------------------|
| U+0049     | :::no-loc text="LATIN CAPITAL LETTER I":::                | **`I`**                   | **<code>&#x0131;</code>**   |
| U+0069     | :::no-loc text="LATIN SMALL LETTER I":::                  | **`i`**                   | **<code>&#x0130;</code>**   |
| U+0130     | :::no-loc text="LATIN CAPITAL LETTER I WITH DOT ABOVE"::: | **<code>&#x0130;</code>** | **`i`**                     |
| U+0131     | :::no-loc text="LATIN SMALL LETTER DOTLESS I":::          | **<code>&#x0131;</code>** | **`I`**                     |

## Sort order

Another example of an area requiring functionality-specific test data is sorting, for which there are some specific examples of data you can use.
These are only a few of the cases that you should prepare test data for.
You should consider the coverage that you require for the target markets you expect to reach.

Under Turkish conventions, dotless "I" (the uppercase "I" or the lowercase "ı") precedes dotted "I" (the uppercase "İ" or lowercase "i").
In Turkish, the letters sort in the order `I ı İ i` (U+0049, U+0131, U+0130, U+0069).
Note that this order is not the same as the order of the values of the letter's Unicode code points.

China has two different sort orders, one by pronunciation and one by stroke order.
The results will vary based on the sort order the user choses.

| Pronunciation Order | Unicode Value | PinYin | Stroke Order | Unicode Value | PinYin |
|--- | --- | --- | --- | --- | --- |
| 䠀 | U+4800  | chang | 𠀀 | U+20000 | he |
| 㠀 | U+3800  | dao   | 㐀 | U+3400  | qiu |
| 䀀 | U+4000  | fan   | 䄀 | U+4100  | huo |
| 䘀 | U+4600  | fu    | 䀀 | U+4000  | fan |
| 𠀀 | U+20000 | he    | 䐀 | U+4400  | ji |
| 䄀 | U+4100  | huo   | 㠀 | U+3800  | dao |
| 䐀 | U+4400  | ji    | 㔀 | U+3500  | qing |
| 𣀀 | U+23000 | lei   | 䠀 | U+4800  | chang |
| 㔀 | U+3500  | qing  | 㘀 | U+3600  | zuo |
| 㐀 | U+3400  | qiu   | 𣀀 | U+23000 | lei |
| 㘀 | U+3600  | zuo   | 䘀 | U+4600  | fu |

## Text processing and storage

When planning your test, put greater importance on test cases that deal with the direct or indirect I/O operations on strings.
You should also give special priority to tests involving text and formatted data (such as numbers, monetary values, date, and time).
Direct input happens when a user enters text in the user interface.
Indirect text input is text fetched from some external source, like a text file, database, or communication channel.
Examples of indirect string input can  host names, user names and email addresses, folder names, and so on.
If your application deals with information of this kind, make sure this data is multilingual when your tests are running.

In a small number of cases the range of characters in the test input might be limited in accordance with certain design limitations.
Set these tests in a globalized environment. See "[Create the test environment](create-the-test-environment.md)."
It might be hard to enter all of these test inputs manually if you do not know the languages in which you are preparing your test data.
A simple Unicode text generator can be very helpful at this point.
