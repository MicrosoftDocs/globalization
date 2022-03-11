---
title: Classify localization issues
description: A wide variety of issues related to globalization and localization can appear in your product. Managing these issues is easier with a taxonomy to classify the issues.
--- 

# Classify localization issues

A wide variety of issues related to globalization and localization can appear in your product.
Managing these issues is easier with a defined taxonomy to classify the issues.
Once a problem is discovered, identifying the class of issue helps to determine its relevance, impact, and priority.
The issue category also helps identify who is responsible for resolving the issue and what must be done to fix it.

In an issue tracking system, the category can be a tag, a field in the issue template, or even an informal notation in the title of an issue.
For example, add `[Commenting]` to the title or description of a problem with the developer comments on a string resource.

Here's one possible taxonomy of localization issues:

| Issue category        | Description |
| --------------------- | ----------- |
| Commenting            | Missing, incorrect, or unclear resource comment. A string has been mistranslated due to lack of context. |
| Untranslated          | String isn't available for translation. The string is hard-coded in source code, not included in scope of localized  resource files, or incorrectly locked. |
| Overtranslated        | A string or part of a string that shouldn't be translated is translated. Resource should be locked or moved out of localization scope. |
| Pseudo                | Pseudolocalization is unavailable or configured incorrectly. |
| EOL                   | Too many or too few languages available. |
| Loc Tool              | An issue with localization tooling. |
| Source error          | Typo, spelling, or grammatical error in the source string. |
| Target error          | Incorrect translation: a typo, spelling, terminology, or grammatical error in a translated string. |
| Concatenation         | String is built from two or more strings, not allowing for ordering differences among languages. |
| String format         | String is constructed through formatting or interpolation that isn't translatable. |
| Numeric format        | Numeric display doesn't follow the user's regional setting. For example, the region is Denmark but numbers are displayed with a period (25.70) instead of a comma (25,70). |
| Currency format       | Currency is displayed with the wrong symbol or incorrect currency unit. For example, a quantity of Euros is displayed without conversion as if it were US Dollars with a dollar sign ($). |
| Date/time             | Date, time, or calendar doesn't follow the user's regional setting. |
| Encoding              | Data isn't stored or read using the correct encoding, or misinterprets a byte order mark. |
| Functional dependency | String serves double duty as both a user interface string and a keyword in an algorithm. The string should be separated into a translated UI string and separate untranslated functional string. |
| Functional error      | Translation causes an error in function. String may be incorrectly exposed to translation, or inadequately commented to describe the constraints the string must satisfy for correct function. |
| Layout                | Elements are clipped or truncated. |
| Bidi                  | Elements that should be mirrored aren't mirrored, and other bidi-related issues. |
| Other                 | Root cause is unknown or the issue doesn’t fit any of the other field value descriptions. |
