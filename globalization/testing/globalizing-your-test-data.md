---
title: Globalizing Your Test Data
description: Test data should be multilingual Unicode text different from the system locale. Use mixed scripts or Unicode-only text to discover codepage dependency
ms.assetid: d5c50681-f03c-4145-b40f-090e887bcb75
ms.date: 04/05/2017
---

# Globalizing Your Test Data

After the environment has been set for globalized testing, your regular test cases must be run with special attention paid to potential globalization problems. The test data must match the test. Use a mix of scripts (Latin, Cyrillic, Armenian, Georgian, Thai, and Indic languages, etc.).

Some particular areas of functionality might require special test data. For example, if the application converts the case of letters, you can verify the functionality with scripts that do not have uppercase and lowercase symbols, such as East Asian scripts or Hebrew. You can also use text with special locale-specific rules for handling case conversion, such as Turkish text with "dotless I." In Turkish both the "dotted" and "dotless" letter "I" exist. "Dotless I" converted to lowercase becomes "i", while "dotted I" converted to lowercase becomes "i".

Another example of an area requiring functionality-specific test data is the sorting procedure, for which there are some specific examples of data you can use. For example of test data involves the sorting order for Turkish "dotless I" versus "dotted I." Under Turkish locale settings, "dotless I" (the uppercase "I" or the lowercase "i") precedes "dotted I" (the uppercase "I" or lowercase "i"). In other words, in Turkish sort order "I" precedes "I", and "i" precedes "i". A further example is that China has two different sort orders, one by pronunciation and one by stroke order. The results will vary based on the sort order the user choses.

|**Pronunciation Order**||||**Stroke Order**|||
|---|---|---|---|---|---|---|
|Character|Unicode Value|PinYin|&nbsp;|Character|Unicode Value|PinYin|
|䠀|U+4800|chang||𠀀|U+20000|he|
|㠀|U+3800|dao||㐀|U+3400|qiu|
|䀀|U+4000|fan||䄀|U+4100|huo|
|䘀|U+4600|fu||䀀|U+4000|fan|
|𠀀|U+20000|he||䐀|U+4400|ji|
|䄀|U+4100|huo||㠀|U+3800|dao|
|䐀|U+4400|ji||㔀|U+3500|qing|
|𣀀|U+23000|lei||䠀|U+4800|chang|
|㔀|U+3500|qing||㘀|U+3600|zuo|
|㐀|U+3400|qiu||𣀀|U+23000|lei|
|㘀|U+3600|zuo||䘀|U+4600|fu|

Some characters in your application have the potential to cause functionality problems. If the application has special handling rules for specific values of characters, some characters incorporated into the data stream will be processed as special control codes. Characters whose code points contain byte sequences that coincide with these special control codes can cause functionality problems.

When planning your test, put greater importance on test cases that deal with the direct or indirect I/O operations on strings. You should also give special priority to tests involving text and formatted data (such as numbers, monetary values, date, and time). Direct input happens when a user enters text in the UI or the text is fetched from some external storage, like a text file or database. Examples of indirect string input are host names, user names, and folder names that include current user names, and so on. If your application deals with information of this kind, make sure this data is multilingual when your tests are running.

In a small number of cases the range of characters in the test input might be somewhat limited, in accordance with the design limitations. Set these tests in a globalized environment. (See "[Creating the Test Environment](creating-the-test-environment.md)".) It might be hard to enter all of these test inputs manually if you do not know the languages in which you are preparing your test data. A simple Unicode text generator can be very helpful at this point.

In addition to globalizing test data that will catch problems and validate functionality, as you conduct your test and view the results you should be able to recognize how some of the globalization problems mentioned in "[Creating the Test Environment](creating-the-test-environment.md)".


