---
title: Keep Sentences in a Single String
description: 
ms.assetid: 93063b70-eb84-40d7-b586-2c2fd9196613
ms.date: 03/16/2016
---

# Keep Sentences in a Single String

You have seen that good localizability practices include minimizing the use of variables, providing unique names for variables, and supplying enough information for the translators to understand the context of what needs to be translated. It is also important to write things out rather than compounding variables together in a string, as in the two previous examples.

Additionally, it is important to keep sentences in a single string. When a sentence is broken up into several strings, the strings do not necessarily appear consecutively in the localizer's string table. It is very time-consuming to piece strings together to form a correct sentence. In addition, it is not possible to merely translate word by word using the same syntax as the original language, since sentence structures differ from language to language. Sentences broken up into several strings coupled with linguistic differences among languages make it hard for autotranslation tools to create one-to-one glossaries without errors

For example, take the following English sentence that has been broken up into three strings:

"When this box is checked, Windows NT does not"
"automatically display the user name of the last person"
"to log on in the Authentication dialog box."
In order to convey the syntactical complexity and additional length in the localized version, the sentence was translated like this in German:

"Wenn dieses Kontrollkästchen aktiviert ist, zeigt"
"Windows NT nicht automatisch den Namen des"
"Benutzers an, der sich zuletzt in dem Dialogfeld"
"Authentifizierung" angemeldet hat."

Translated back into English, this sentence literally means:

"When this controlbox checked is, -plays"
"Windows NT not automatically the name of
"the user -dis, who him/herself last in the dialog box"
"Authentication" logged has."
Keeping the sentences in single strings allows automated translation tools to help your translators be more precise, more productive, and thus allow more cost savings for you.


