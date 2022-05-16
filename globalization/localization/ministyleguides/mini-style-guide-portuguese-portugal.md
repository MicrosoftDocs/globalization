---
title: Portuguese (Portugal) Localization Style Guide
description: Are you helping with translation into Portuguese (Portugal), but don't have time to study all of the Portuguese (Portugal) Style Guide? Here are the ten most important aspects.
ms.date: 03/19/2019
---

# Top 10 Tips for Microsoft Translation into Portuguese (Portugal)

Are you helping with translation into Portuguese (Portugal), but don't have time to study all aspects of the Portuguese (Portugal) Style Guide on the [Microsoft Language Portal](https://www.microsoft.com/Language/StyleGuides)? Here are ten of the most important aspects to keep in mind.

## 1. General

- Translate meaning, not words. If a translated sentence is hard to understand or incomprehensible to you (or anyone else), it's likely that you didn't understand it. Always make sure that you understand every single word in the source text, and research how the same things are said in Portugal.
- When a glossary term is very generic, try to expand the translation slightly to make your translation unambiguous. For example, translating drive simply as unit doesn't always convey an unambiguous meaning. In such cases, consider translating it as _:::no-loc text="unidade de disco":::_, _:::no-loc text="unidade de banda":::_, _:::no-loc text="unidade USB":::_—whatever is applicable in the specific context.
- To search for terms only on Portuguese (Portugal) websites, add **site:.pt** to your search string in the browser.
- Words to watch out for:

|English|Portuguese (Portugal)|
|---|---|
|character|:::no-loc text="caráter":::|
|characters|:::no-loc text="carateres":::|
|convert to|:::no-loc text="converter em":::|
|display|:::no-loc text="mostrar"::: (what the computer displays to the user)
| |:::no-loc text="visualizar"::: (what the user sees on the computer)|
|download|:::no-loc text="transferir":::|
|make sure|:::no-loc text="certifique-se de que":::|
|please|[omit]|
|required|:::no-loc text="necessário":::|
|set to|:::no-loc text="definir como":::|
|website|:::no-loc text="site":::|

## 2. Spelling

Post-reform Portuguese (Portugal) spelling rules apply.

When a word can be spelled in two ways, apply the spelling that reflects standard Portuguese (Lisbon) pronunciation. If the dictionary lists two acceptable variations, for example, the translation of character, refer to the approved glossaries.

## 3. Capitalization

Follow the capitalization style (that is, Title Case or Sentence case) that's used in the source text.

Example:

_English_: Do not use Print Without Saving so as not to lose your work.

_Our style_: :::no-loc text="Não use a opção Imprimir Sem Guardar para não perder o seu trabalho.":::

When a single source word translates into multiple target words (for example, Desktop), make sure to capitalize all applicable words (:::no-loc text="Ambiente de Trabalho":::).

## 4. Acronyms 

For the plural form of acronyms, add a lower-case _s_.

Example:

|English|Portuguese|
|---|---|
|Enter the URL.|:::no-loc text="Introduza o URL.":::|
|Enter the URLs.|:::no-loc text="Introduza os URLs.":::|
|Enter a URL.|:::no-loc text="Introduza um URL.":::|
|Enter URLs.|:::no-loc text="Introduza URLs.":::|

## 5. Audience

All audiences must be addressed using formal wording (verb in third-person singular). An exception is made for gaming audiences, which are to be addressed informally (second-person singular).

## 6. Preposition (:::no-loc text="regência verbal":::)

Examples of incorrect versus correct prepositions:

Example:

|English|Not our style|Our style|
|---|---|---|
|convert (something) to|:::no-loc text="converter para":::|:::no-loc text="converter em":::|
|register (something) with|:::no-loc text="registar com":::|:::no-loc text="registar em":::|
|set (something) to|:::no-loc text="definir para":::|:::no-loc text="definir como":::|

## 7. Possessive Pronouns

Only translate the possessive pronouns his/her/its and their as _:::no-loc text="respetivo(s)":::_ when the intended meaning is indeed corresponding. Some translators believe that using _respetivo_ to translate the English possessive pronouns is common practice, but more often than not it results in an incorrect or ambiguous translation. Just use _:::no-loc text="seu(s)":::_ or _:::no-loc text="sua(s)":::_ unless this results in ambiguity. Otherwise, use _:::no-loc text="dele(s)":::_ or _:::no-loc text="dela(s)":::_, or omit the pronoun altogether where appropriate. Note that ambiguous translations are penalized in reviews.

## 8. Quotation Marks

In a sentence that includes a quotation, place the end-of-sentence mark, such as a period or question mark, outside the quotation mark unless the punctuation is part of the quotation. In that case, place the punctuation inside the quotation marks.

## 9. Numbers

When translating large numbers, please remember that English (US), Portuguese (Brazil) and Portuguese (Portugal) number names differ greatly.

Example:

|English (US)|Portuguese (Brazil)|Portuguese (Portugal)|
|---|---|---|
|million|:::no-loc text="milhão":::|:::no-loc text="milhão":::|
|billion|:::no-loc text="bilião":::|:::no-loc text="mil milhões":::|
|trillion|:::no-loc text="trilião":::|:::no-loc text="bilião":::|

As regards separators, the decimal separator is a comma, and the thousands separator is a period.  

Example:

20.356,51

## 10.  Infinitive vs. Imperative

All instructions to the user must be translated using the imperative (_:::no-loc text="faça":::_), not the infinitive (_:::no-loc text="fazer":::_). For instance, a dialog box presents the user with the following instructions.

|English|Our style|
|---|---|
|Open the file to edit its contents.|:::no-loc text="Abra o ficheiro para editar o conteúdo.":::|
|Close the file to continue|:::no-loc text="Feche o ficheiro para continuar":::|

All commands from the user to the software as well as all descriptions of commands, keystroke functions, and so on, must be translated using the infinitive (:::no-loc text="fazer":::).

Example:

|English|Our style|
|---|---|
|Open file to edit contents|:::no-loc text="Abrir ficheiro para editar conteúdo":::|
|Open the file and edit contents.|:::no-loc text="Abrir ficheiro e editar conteúdo.":::|
|Open\nOpen file in Excel|:::no-loc text="Open\nAbrir ficheiro no Excel":::|

Example:

|English|Our style|
|---|---|
|Open\nOpen file in Excel|:::no-loc text="Open\nAbrir ficheiro no Excel":::|
|/QUERY Query current session login mode.\n|:::no-loc text="/QUERY Consultar o modo atual de início de sessão.\n":::|
|Enable, disable, or drain session logins.\n\n|:::no-loc text="Ativar, desativar ou drenar inícios de sessão.\n\n":::|
|PAGE UP\tMove 3 lines up in the text|:::no-loc text="PAGE UP\tSubir 3 linhas no texto":::|
