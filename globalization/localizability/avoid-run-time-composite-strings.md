---
title: Avoid Run-Time Composite Strings
description: 
ms.assetid: 9b878fc7-44c8-4adb-94a5-13164d135eaf
ms.date: 06/28/2016
---
# Avoid Run-Time Composite Strings

When creating strings for output, well-intentioned programmers use a coding trick that has been passed down from generation to generation of developers as a good coding practice. That trick is using text strings with variables that get composed at the application's run time. Thus you see code as shown here that is written to produce the following English text:

-   "Are you sure you want to delete the file?"
-   "Are you sure you want to delete the directory?"
-   "Are you sure you want to delete the subdirectory?"

```C++
char szString[] = "Are you sure you want to delete the ";

char szFinalString[cbMaxSz]= szString + szDelObject + "?";
```

Note that szDelObject is a variable that can contain either a file, directory, or subdirectory. This practice works well for the programmer, but all the translator sees in the resource file is "Are you sure you want to delete the "; the translator has no idea what is being deleted. The value of the variable often determines whether a different syntax or definite article needs to be used, depending on the item to be deleted. The reason is that in some languages nouns have gender. For instance, in German nouns can be masculine, feminine, or neuter. In Romance languages such as French or Portuguese, nouns are either masculine or feminine. Depending on the gender of the noun in such languages, the definite article that precedes the noun will vary. For example, French uses "le" in front of masculine nouns (such as "le fils" for "the son") and "la" in front of feminine nouns (such as "la fille" for "the daughter"). Thus for the previous code, a French translator would not know whether to use "le" or "la," because the actual value of the variable-in this case, the noun-is not specified. The best way to avoid this ambiguity is to write out each sentence completely, if possible. This way the translator knows the context of the sentence and can translate it correctly. Thus in your resource store you would have:

```C++
Del_File = "Are you sure you want to delete the file?";

Del_Dir = "Are you sure you want to delete the directory?";

Del SubD = "Are you sure you want to delete the subdirectory?";
```

Another potential shortcut involves declaring a single string, such as "none," "blue," or "first," and displaying it in a number of different contexts-on a menu, in a dialog box, and perhaps in several messages. The problem with using "all-purpose" strings is that in European languages, adjectives (and some nouns) have anywhere from 4 to 14 different forms (for example, masculine, feminine, and neuter singular; and masculine, feminine, and neuter plural) that must match the nouns they modify. For instance, in Spanish the word "first" can be conveyed by the words "primero," "primera," "primer," "primeros," and "primeras," depending on the gender and number of the noun or the particular sentence structure. A single string displayed in different contexts will be correct in gender and number in some cases but incorrect in others. The user will consider such a translation amateurish. Again, the way to handle this problem is to have a separate string for the same word used in a different context, such as the following strings:

```C++
Menu_open = "open"
        
Dialog_open = "open"
        
Button_open = "open"
```


