---
title: Message formatting
description: Formatting messages requires careful consideration of a target language that may have different word order, gender, number (plurals), and other characteristics.
ms.date: 3/26/2024
author: jowilco
---

# Message formatting

You can think of an application that is ready for localization as having two conceptual blocks: a block that contains all user visible elements and a block that contains executable code. The first block contains only localizable user-interface elements such as strings, typically stored in *resource files*. The second block contains only the application code to be used by all supported cultures.

To add support for one or more additional languages or cultures, you can create copies of the resource files translated into the appropriate language for the target culture. There are several methods to determine a [user’s preference](../locale/user-preferences.md) for which language resource files should be used and which language resource files should be used if a [preferred language resource isn't available](../locale/fallback.md).

Each programming language or framework specifies the format for resource files; however, a common resource file format contains string resources as *name/value* pairs. *name* is a string that identifies the resource, and *value* is the resource string that is returned when you pass *name* to a resource retrieval method. *value* can contain any strings; however, there are best practices for how strings should be written so that they're easily translated.

## String authoring best practices and issues

### Concatenation

In the early days of software development, memory was often a limiting factor. A common practice was to author text strings with variables that were composed at the application’s run time to generate sets of strings like:

- "Are you sure you want to delete the file?"
- "Are you sure you want to delete the directory?"
- "Are you sure you want to delete the subdirectory?"

```C+
// resource file:

delete_prompt = "Are you sure you want to delete the ";
file_object = "file";
dir_object = "folder";
subdir_object = "subfolder";

// code:

char message_prompt[MAX_MSG];
strcpy(message_prompt, delete_prompt);
strcat(message_prompt, subdir_object);
strcat(message_prompt, "?");

// display message_prompt  to user
...
```

This practice is called *concatenation* and works well to reduce the number of characters needed to display the messages. However, when the translator needs to translate `delete_prompt` they might only see the text `"Are you sure you want to delete the "` without having any idea what is being deleted.

With a few exceptions, memory isn't the primary consideration when authoring resources. Best practice is to **never** concatenating strings. Even when there are many cases, write out each sentence completely.

```cpp
deleteFile = "Are you sure you want to delete the file?";
deleteDirectory = "Are you sure you want to delete the directory?";
deleteSubDirectory = "Are you sure you want to delete the subdirectory?";
```

See [Concatenation](concatenation.md) for more examples of patterns of localization issues resulting from concatenation.

### Repurposing strings

Another way of reducing the number of strings in an application is to use the same string in different contexts, such as for a menu item, a button, and as part of an error message. Even when the string is identical in different contexts in English that might not be the case in other languages.

For example, ```Bookmark`` in English could be a noun or a verb, so could potentially be used in different contexts. However, the translations for the verb and the noun might differ, so a single string wouldn't be sufficient.
Instead, you should use a separate string for every instance.

### Strings and variables

Most programming languages have methods or functions that allow programmers to insert variables into specific locations in strings. For example, .NET has the [String.Format](/dotnet/api/system.string.format) method. The specific locations where variables can be inserted might be called *format items*, *replacement fields*, *format elements*, *format specifiers*, or similar. For this section, the generic term *placeholder* is used.

There are several types of placeholders that can be used, depending on the programming language or framework.

- Named placeholders. For example, `{myvariable}` indicates that the value of the `myvariable` argument will be inserted at this location. The variable names should be meaningful to provide context to the translators.
- Position specifier. For example, `%2` indicates that the second argument in the list of arguments will be inserted at this location.
- Type specifier. For example, `%s` indicates that a string variable is expected while `%d` indicates that a decimal integer is expected.

Combinations of these placeholder types might also be available, depending on the programming language or framework. For example, Java supports format specifiers like `%1$s` indicating that the first argument in the list of arguments should be inserted in this location as a string.

For localization, it's helpful that translators have as much control over the location of placeholders as possible. Named placeholders make it much easier for translators to understand how the placeholder will be used. For example, you might need a string like `Available Monday to Friday, from 8 AM to 5 PM Central Time.`. This string could be generated using:

```text
Available {firstWeekDay} to {lastWeekDay}, from {startTime} to {endTime} {timeZone}
Available %s to %s, from %s to %s %s
```

It would be quite challenging for translators to understand how to translate the second version.

The order for placeholders might also need to change for translation.

```text
Selected {0} out of {1}
Selected %d out of %d
```

In the first version, a Japanese translator could reorder the variables for a translation like: `{1} 個中 {0} 個が選択されました`. With the second version, a less natural translation might need to be used, such as: `%d/%dが選択されました`

In summary, the preference for localization is:

- Named placeholders: `{firstName}`
- Placeholders that specify the order/position and the type: `%1$d`
- Numbered placeholders: `{3}`
- Placeholder that only defines format: `%s`

### Variables

As discussed in [Strings and variables](#strings-and-variables), some languages and frameworks support placeholders that allow the developer to specify the format of each argument. The methods or functions used to format the strings containing the placeholders often support specifying the locale to be used, with the format specifier determining the layout that might include using grouping separators appropriate for the locale. In other words, the translator might have limited control over how the variable is displayed by modifying the format specifier.

For named placeholders and position-specific placeholders, the formatting of the arguments needs to take place in the code. The developer has full control over ensuring that the correct locale is used, and the format for strings, dates/times, and numbers is correct. For languages and frameworks that only support type specifiers, you might also consider implementing all the formatting in code and displaying all results as strings.

#### Dates/times, numbers, and currency

You should use locale-aware methods/functions for formatting numbers, currency values, and dates/times. Avoid making any assumptions about how any of these types of values are formatted.

For example, you could choose to have a % (percent sign) as part of your string `You have used {amount}%`. A translator translating this string into French would need to add a nonbreaking space before the %, while in Turkish the % would appear before the value. Rather than relying on the translator to implement the language-specific formatting, .NET supports a locale-aware [percent format specifier](/dotnet/standard/base-types/standard-numeric-format-strings#PFormatString) that correctly formats the number according to the locale.

#### Strings

When using placeholders with string arguments, you need to be careful that the string arguments:

1. Won't need to change based on the grammar of the language
1. The string into which the string arguments are being inserted won’t need to change based on the grammar of the language.

We can see this issue in English: `You have purchased a {fruit}.` This string is appropriate for `banana`, but should be `You have purchased an {fruit}` for `orange`.

In general, inserting text into other strings can have similar issues to concatenation. Where possible, it's best practice to have separate strings for every combination; however, this isn't always practical. For more information, see [Gender and grammatical articles](#gender-and-grammatical-articles) and [Pluralization](#pluralization).

### Untranslatable content

Where possible, you should avoid mixing untranslatable content (for example, HTML code) with translatable text. For example, `Click {startlink}here{endlink} to proceed.` rather than `Click <a href="mytarget">here</a> to proceed.`. While computer-aided translation (CAT) tools do try to protect any code or markup in translatable text from being edited by translators, avoiding the issue is better.

For HTML, the `alt` attribute is a case where translatable text and code are mixed. You should consider whether to extract translatable text, like the value of the `alt` attribute, as a standalone string, or whether it is worth making the entire HTML string available for translation.

### Providing context

Some resource file formats support adding [metadata](contextual-metadata.md) to each resource. You should take advantage when this feature is available. The two most valuable pieces of information for translators are:

1. For short strings, especially when the context isn't readily apparent, explain how the string is used. As a guideline, if a string isn’t a complete sentence, then a comment is often helpful for the translators.
1. If a string contains placeholders, explain each argument, and describe the range of values.

### Punctuation and spacing

In general, you should never [concatenate](concatenation.md) text fragments. It can be more tempting to concatenate complete sentences; however, there are still potential risks. In English, sentences end with a period (U+002E FULL STOP) and sentences are separated with spaces. This isn't the case with all languages so you shouldn’t assume that sentences end with a terminator, or that the terminator is an (English) period. You should also not assume that sentences are separated with space characters.

You should support other differences in punctuation marks. For example, French uses a (nonbreaking) space before a question mark and to separate quotation marks from the quoted text. The characters used to indicate quotes or parentheticals frequently differ from English.

### Gender and grammatical articles

Languages like German, French, and Russian assign a gender to all nouns. If you replace the noun in a sentence and the gender of the replacement noun is different, other changes to the sentence are often required. In French, this might be limited to the definite or indefinite articles. In Russian, which is an inflected language, you might need to change the ending of the noun depending on the grammatical case and gender. Articles in English can also change depending on whether the noun starts with a vowel (an airplane) vs a consonant (a car).

It's best practice to avoid using variables to add words or phrases into sentences. If possible, have separate strings for each sentence that can be constructed. Where this isn't possible you'll have to consider how the grammar in the source and target languages are affected by substituting words. Translators have become skillful in rewording source text so that the grammar in the translated text can handle differences in gender; however, by adapting the source text to work around these differences can result in translations that aren't as elegant as the original source text.

### Pluralization

A common construction in English strings is to try to handle singular and plural values in a single string.

```text
mystring = You have {count} apple(s).
```

The `(s)` is a compromise to support a value of 1 for `count`. To avoid this compromise, you could use two strings.

```text
mystring_singular = You have 1 apple.
mystring_plural = You have {count} apples.
```

However, some languages don’t change the noun as `count` changes, while other languages have different rules when `count` is zero, one, two, a small number, and a large number. Pluralization can be a complex topic for localization, so it's covered as a separate article in [Pluralization](pluralization.md).
