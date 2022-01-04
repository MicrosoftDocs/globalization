---
title: When variables are necessary, use unique names
description: Although translators would love to have strings with no variables as well as strings that are repeated for usage in different contexts, there are times when it is necessary to use variables.
ms.assetid: 889f8577-b7a3-42f1-8c2f-07f8b60f6078
ms.date: 06/28/2016
---
# When variables are necessary, use unique names

Although translators would love to have strings with no variables as well as strings that are repeated for usage in different contexts, there are times when it is necessary to use variables.
When there is only one variable in a string, like in the example that involved deleting a file, directory, or subdirectory, it is best to use a function that allows you to at least put a placeholder in the text.
Thus the earlier example would become:

```cpp
delete_prompt = "Are you sure you want to delete the %s?"; // %s is one of 'file', 'folder', 'subfolder'
```

To help the translators, document all the values that the variable can be.
This way they will know what goes in the variable and will be able to translate it using the correct syntax and grammar for the target language.

Because word order can vary significantly from language to language, using identical placeholders can cause problems if you have a string that has two or more variables.
For example, suppose you have the following string:

```cpp
memory_error = "Not enough memory to %s the file %s."
```

The first `%s` is a function like open, close, or save and the second `%s` is the name of the file you are trying to open, close, or save.
The problem here is the implicit order of the variables.

Thus one of the possible sentences generated with this English string might be:

```cpp
"Not enough memory to open the file filename1."
```

Now, Suppose you plan to translate this text into Swedish and Finnish.

The Swedish translation causes no problem because its translation is:

```cpp
"Det finns inte tillräckligt med minne för att öppna filen FileName1."
```

THe order of the variables is the same as in English.
Notice that the command "open" (" [öppna]") comes before the file name.

Now look at the correct Finnish translation:

```cpp
"Liian vähän muistia tiedoston FileName1 avaamiseen."
```

Notice here that the command "open" (" [avaamiseen]") comes _after_ the file name.

However, when you run the program, the result is:

```cpp
"Liian vähän muistia tiedoston avaamiseen FileName1."
```

The message is wrong because the order of the variables in the translation do not correspond to the implicit order of  processing `%s` in most programming languages.
The localizer cannot fix this because they cannot change the order of the parameters to the string formatting call in the code.
Therefore, it is better to use functionality where you can specify the variable order, as in this English string:

```cpp
"Not enough memory to %1 the file %2."
```

Here, the translator is able to put the placeholders int he correct order to generate a grammatical and correct result.

The Swedish and Finnish translation, respectively, would be:

```cpp
"Det finns inte tillräckligt med minne för att %1 filen %2."

"Liian vähän muistia tiedoston %2 %1."
```

This can be further improved using functionality where placeholders have a name that can convey usage information to the translator:

```cpp
"Not enough memory to {operation} the file {filename}."
```