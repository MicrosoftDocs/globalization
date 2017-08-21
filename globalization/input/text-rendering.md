---
title: Text Rendering
description: When creating a locale–aware application, you'll need to consider handling of linguistic nuances.
ms.assetid: 3bf55477-13ea-41ca-92dc-f4194b4928a5
ms.date: 05/01/2017
---
# Text Rendering

Text rendering is the process of converting a string to a format that is readable to the user. For simple scripts, this process is straightforward. For more complicated scripts, there are many factors that lead to the correct rendering of a string.

-   Capitalization, Uppercasing, and Lowercasing
-   Text shaping, including complex text layout, for languages where characters change shape depending on context.
-   Direction

## Capitalization, Uppercasing, and Lowercasing

When creating a locale-aware application, you'll need to consider handling of linguistic nuances. These nuances might seem trivial, but could have a large impact on application design and functionality. For example, Windows allows you to convert characters into either uppercase or lowercase equivalents. Some applications use this feature to automatically convert the first letter of every sentence into uppercase or to assume that certain types of words should always be capitalized. In Russian, however, names of the days of the week are never capitalized–capitalizing the word for "Wednesday" changes the meaning to "environment," and capitalizing the word for "Sunday" changes the meaning to "resurrection".

In the past, as localized products were developed, language-sensitive issues—such as casing—were sometimes handled with what were thought of as well-designed, intelligent algorithms. For example, an uppercasing macro that relies on the code–point numbers of ASCII characters and the linear relationship between uppercase characters (A = 41) and lowercase characters (a = 61) can be written as:

```C++
#define ToUpper(ch) ((ch)&lt;='Z' ? (ch) : (ch)+'A' - 'a')
```

You can see the problems this English–centric approach presented when representing uppercasing in non–Latin scripts or languages with accented characters where, for example, character mapping doesn't follow the assumed relationship between lowercase and uppercase characters. There are several other reasons why algorithmic solutions for case-folding does not cover all occurrences.

First, some languages do not have a one–to–one mapping between their uppercase and lowercase characters. For instance, the uppercase equivalent of the German ß is "SS." Second, some characters have different mappings depending upon the language in which they are used. Most non–Latin scripts do not even use the concept of lowercase and uppercase. Where are the capital letters in the strings below?

-   पूंजी पत्र कहाँ हैं? \(Devanagari script/Hindi)
-   大寫字母在哪裡？ \(Traditional Chinese)
-   மூலதன கடிதங்கள் எங்கே? \(Tamil)
-   (Arabic) أين هي الحروف الكبيرة؟ 
-   ບ່ອນທີ່ຈົດຫມາຍນະຄອນຫຼວງມີຫຍັງແດ່? \(Lao)
-   (Hebrew) היכן הם אותיות רישיות?
-   대문자는 어디 있습니까? \(Korean)
-   ಅಕ್ಷರಗಳಲ್ಲಿ ಎಲ್ಲಿ? \(Kannada)
-   ตัวอักษรตัวใหญ่อยู่ที่ไหน \(Thai)
-   কোথায় বড় হাতের অক্ষরে? \(Bangla)
-   სად არიან ასოებით? \(Georgian)
-   જ્યાં મૂડી અક્ષરો છે? \(Gujarati)

Developers are better served by using an API (e.g., [ToUpper()](https://msdn.microsoft.com/en-us/library/24kc78ka(v=vs.110).aspx)) if they need to capitalize text. Keep in mind that some capitalization is particular to a language, so designating the language to the API is an important step. Such as for addressing the [Turkish-İ] problem](https://msdn.microsoft.com/en-us/library/ms973919.aspx#stringsinnet20_topic5). For English, the lowercase "i" maps to a dotless uppercase letter: "I." However, in Turkish the lowercase "i" maps to a dotted uppercase letter: "İ."

## Text Shaping

Most platforms and browsers support correct text shaping automatically or by calling APIs (such as [DirectWrite](https://msdn.microsoft.com/en-us/library/windows/desktop/dd371554(v=vs.85).aspx)), but testers and developers should be aware that scripts’ glyph shapes may change depending on the context, and should ensure correct behavior in applications.

### Ligatures

The simplest example of such shaping is a ligature. A ligature is a combination of two or more glyphs to form a single glyph. English uses the same process in typesetting (for example, ff, fi, fl, ffl, ffi), although far less frequently than other scripts. It is common in many scripts for multiple characters to combine into a single shape. The rules of ligature used in ligature processing can be very complex in some scripts, such as Arabic, while much simpler in others, such as the Latin script. These rules not only depend on the individual characters of a given script, but also on the selected font used to draw them. Depending on the script, certain fonts are known to define hundreds of ligatures, while some other fonts do not use ligatures at all. Ligatures may cause side effects such as cursor movement, text selection, and the positioning of diacritics relative to characters in scripts that support diacritics.

A ligature example is the diphthong in English in which two vowels, “A” and “E”, unite to create a single sound glyph as following:

Æ = A + E ← ALT + 0198

A typical example is the ligature of Arabic Lam and Alef as shown below (reading from right-to-left):

ل + ا = لا ← ALT + 65275

| **Individual Characters** |  **Without Ligatures** |  **With Ligatures** |
|----------------------|-------------------|-----------------|
| ل م ح                     |  لمح                   |  لمحـ               |

### Contextual Shaping

In some scripts the glyph displayed depends on the surrounding characters. A single Arabic character, for example, can take different shapes if it’s the first, middle, or last character in a word. Contextual shaping is the formation of correct sequences of characters, given these contexts.

In Greek, the sigma character changes depending on whether the letter is at the beginning or the end of the word, as in the following example.

σ οφό ς

### Character Reordering

Character reordering is the rearrangement of characters in sequence from their logical order (the order in which they are input) to their visual order (the order in which they are displayed). Some scripts, such as Devanagari and Tamil, require reordering, because vowel signs often appear to the left of, below, or above a character that they follow in logical order.

कूत = क + ि + ै + ू + त

### Character Stacking

Stacking or combining multiple characters into one “pile” is another issue that must be addressed for some scripts. The Unicode standard has many combining characters, but in the case of European languages, they are optional, or can be replaced with pre-composed characters. This is not the case with languages or scripts. This issue may also be observed when the Latin script is used to represent Vietnamese.

ế = e + ̂ + ́

For Thai, a syllable usually consists of a consonant followed by a vowel and optionally a tone mark, the latter two of which are sometimes displayed above (or in some cases, below) the consonant.

ที่อยู่ = ท + ี + ่ + อ + ย + ู + ่

## Direction

Direction specifies the reading order of a string. Some writing systems may be written in more than one direction. However, for simple text—such as an input field—generally, there are two directions to be concerned with: left-to-right (LTR) and right-to-left (RTL).

Each character in Unicode has an associated directional property. We may classify the character directionality as following:

**Strongly typed**: This includes the normal character set. For example, English or Arabic

**Neutral**: This includes all punctuation characters such as periods, commas, (, %, @ , \[, !, etc.

**Weak**: This includes numerals

Latin characters have a left-to-right (LTR) Unicode directional property and hence a sequence of Latin characters will render or display from left to right. On the other hand, Arabic—a right-to-left language (RTL)—characters have an RTL Unicode directional property. Hence, a sequence of Arabic characters will render from right to left. We say that the character set of both a left to right language and a right to left language are strongly typed. Therefore, the [bidi algorithm](http://www.unicode.org/reports/tr9/) will not have a problem displaying a mix of LTR and RTL languages. It simply renders each group of characters as a separate directional run and displays it in the right direction.

For these scripts, the logical order (the order in which the user enters text with a sequence of virtual-key inputs) and the visual order (the order in which characters are represented to the user) are different in most cases.

![Bidirectional text (Arabic) where the logical order (first row) and the visual order (second row) are not of the same sequence of characters](/media/hubs/globalization/IC868519.jpg "Bidirectional text (Arabic) where the logical order (first row) and the visual order (second row) are not of the same sequence of characters")

**Figure**: Bidirectional text (Arabic) where the logical order (first row) and the visual order (second row) are not of the same sequence of characters

### Neutral Characters

Unlike strongly typed characters, spaces and punctuation characters can be used in either LTR or RTL languages and do not have LTR and RTL forms in Unicode. Hence, they are classified as Neutral.

The bidi algorithm renders neutral characters by looking the characters surrounding them. A neutral character may fall between two characters of the same directionality (LTR or RTL) or between a strongly typed LTR and a strongly typed RTL characters.

### Between Similar Directionality

When a neutral character falls between two characters of the same directionality, it will assume the same directionality as the surrounding characters. Hence the bidi algorithm will render it as one run with the same directionality.

| **LTR Examples:** |  first second |  first&second |  first,second |
|-------------------|---------------|---------------|---------------|
| **RTL Examples:** |  عربي سلام     | عربي&سلام     |  عربي,سلام       |

### Between Opposite Directionality

When a neutral character falls between two characters of the opposite directionality, it will assume the overall directionality of the whole paragraph or context. The following example shows the different scenarios of how the bidi algorithm renders text with neutral characters between characters of different directionalities: same directionality as the surrounding characters. Hence the bidi algorithm will render it as one run with the same directionality.

| **Typed Text**               |  **Display in LTR Paragraph** |  **Display in RTL Paragraph** |
|------------------------------|-------------------------------|-------------------------------|
| “First” then “&” then “عربي” |  [First&]عربي                 |  first [&عربي]                |
| then “&” then “Last”“عربي”   |  [&Last]عربي                  |  [عربي&]Last                  |

Notice how the neutral character in each column is attached to a different character set. For example, in the first row, the neutral character is treated as an English character in the first column (assigned LTR directionality), but as an Arabic character in the second column (assigned an RTL directionality).

### Weak Characters

Numbers in RTL languages run from left to right. The bidi algorithm classifies them as having weak directionality and treats them differently from characters and punctuation. Numerals will simply assume the directionality of the preceding character. The following example shows how numerals are displayed with mixed text. Assume an LTR paragraph.

Both lines were typed in the following color order: red, black, blue, green, and orange:

[one​] [two​] [ثلاثة​] [four​] [خمسة]

[one] [two] [خمسة] [4] [ثلاثة]

Notice that by simply typing “4” instead of “four,” the number will follow the directionality of the preceding character, and hence will follow the blue Arabic word (three) and appear to the left of it as continuation of the RTL text run.

### Directionality Control Marks

There are hidden directionality control characters that the user may explicitly invoke to override the bidi algorithm and force a desired reading order.

The following four characters are used in pairs. One is used first and indicates the start of a range of text; the range is terminated by the last (PDF) character in each case.

-   U+202A: LEFT-TO-RIGHT EMBEDDING (LRE)
-   U+202B: RIGHT-TO-LEFT EMBEDDING (RLE)
-   U+202D: LEFT-TO-RIGHT OVERRIDE (LRO)
-   U+202E: RIGHT-TO-LEFT OVERRIDE (RLO)
-   U+202C: POP DIRECTIONAL FORMATTING (PDF)

Two other invisible but non-embedding directional control characters provided by Unicode do not usually have corresponding markup and should be used either in character or escaped form. Note that they are less problematic because they are used singly, not in pairs to delimit ranges of text like the other control characters we have discussed.

-   U+200E: LEFT-TO-RIGHT MARK
-   U+200F: RIGHT-TO-LEFT MARK

## Implications for Cursor Movement

All these text rendering issues can have implications for cursor movement. Unlike Latin script, which requires forward and backward movement of the caret only, some scripts demand that characters be displayed above, below, or to the left of previous characters. In Thai, for example, if the cursor is positioned after a base consonant, vowel, and tone mark, the cursor should skip back over all three characters when the user types the back arrow.

![Cursor positioning](/media/hubs/globalization/IC868521.png "Cursor positioning")

**Figure**: Cursor positioning

For bidirectional scripts, the direction of the cursor movement may change depending on the direction of the text involved. For example, when using the arrow keys to move from right to left through Arabic and then English text in the same sentence, the insertion point moves in a right-to-left manner through the Arabic text and then continues at the rightmost character in the English word and progresses in a right-to-left manner.

![Pressing the right-arrow key through Latin and Hebrew text](/media/hubs/globalization/IC868520.png "Pressing the right-arrow key through Latin and Hebrew text")

**Figure**: Pressing the right-arrow key through Latin and Hebrew text.

Similarly, backspace, highlighting, and double-clicking should work correctly for the text properties.

## Ensure Search is International Aware

Search should use a suitable buffer size to accept multi-byte characters. Word wrapping should not truncate multi-byte characters. Double-clicking on multi-byte characters should highlight the entire word.

-   Search needs to support languages without word breakers, e.g. Japanese and Chinese.
-   For most search implementations, the functionality comes from SQL, for more advanced implementations you must specify the appropriate collation for the language being searched.
-   For more information on line and word breaking, please see [Line and Word Breaking](https://msdn.microsoft.com/globalization/mt662334).


