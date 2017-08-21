---
title: When Variables Are Necessary, Use Unique Names
description: 
ms.assetid: 889f8577-b7a3-42f1-8c2f-07f8b60f6078
ms.date: 06/28/2016
---
# When Variables Are Necessary, Use Unique Names

Although translators would love to have strings with no variables as well as strings that are repeated for usage in different contexts, there are times when it is necessary to use variables. When there is only one variable in a string, like in the example that involved deleting a file, directory, or subdirectory, it is best to use a function that allows you to at least put a placeholder in the text. Thus the earlier example would become:

```
Del_File = "Are you sure you want to delete the %s"
```

To help the translators, document all the values that the variable can be. This way they will know what goes in the variable and will be able to translate it using the correct syntax and grammar for the target language.

Because word order can vary significantly from language to language, using identical placeholders can cause problems if you have a string that has two or more variables. For example, suppose you have the following string:

```
Memory_Error = "Not enough memory to %s the file %s."
```

The first %s is a function like open, close, or save and the second %s is the name of the file you are trying to open, close, or save. Thus one of the possible sentences generated with this string might be:

```
"Not enough memory to open the file filename1."
```

Suppose you plan to translate this text into Swedish and Finnish. The Swedish translation causes no problem because its translation is:

```
"Det finns inte tillräckligt med minne för att öppna filen FileName1."
```

Notice that the command "open" (" [öppna]") comes before the file name. Now look at the Finnish translation:

```
"Liian vähän muistia tiedoston FileName1 avaamiseen."
```

Notice here that the command "open" (" [avaamiseen]") comes after the file name; but in most programming languages if you used %s for both your variables (as in the earlier example), your program string would actually be created as:

```
"Liian vähän muistia tiedoston avaamiseen FileName1."
```

This is because the variable in the original call to output this string was in the order of command first, file name second. Therefore, it would be better if you had some way to show variable order, as in this string in English:

```
"Not enough memory to %1 the file %2."
```

The Swedish and Finnish translation, respectively, would be:

```
"Det finns inte tillräckligt med minne för att %1 filen %2."

"Liian vähän muistia tiedoston %2 %1."
```


