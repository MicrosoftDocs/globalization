---
title: Spanish (Neutral) Localization Style Guide
description: Are you helping with translation into Spanish (Neutral), but don't have time to study all aspects of the Spanish (Neutral) Style Guide on the Microsoft Language Portal? Here are ten of the most important aspects to keep in mind.
ms.date: 07/16/2019
---

# Top 10 Tips for Microsoft Translation into Spanish (Neutral)

Are you helping with translation into Spanish (Neutral), but don't have time to study all aspects of the full [Spanish (Neutral) Style Guide](http://download.microsoft.com/download/c/8/0/c80371fa-bc89-46a7-883d-071d59f0c24c/spa-neu-StyleGuide.pdf)? Here are ten of the most important aspects to keep in mind.

## 1.	Translate meaning not words

The language in Microsoft products should have the "feel" of a product originally written in Spanish, with idiomatic syntax, while keeping a high level of terminology consistency for the best possible user experience. To achieve a fluent translation, word-for-word or literal translations should be avoided. If the concepts are translated without an overall understanding of the text, the content will not sound natural. To make the text easily understood, try to understand the whole intention of the sentence, paragraph, or page, and then rewrite as if you were writing the content from scratch. 

**Examples**

_English_: Rediscover your keyboard

_Our style_: <span lang="es-ES">Una nueva forma de usar tu teclado</span>

_Not our style_: <span lang="es-ES">Redescubre tu teclado</span>

<br>

_English_: Simple sharing with anyone.

_Our style_: <span lang="es">Comparte fácilmente con quien quieras</span>

_Not our style_: <span lang="es">Uso compartido simple con todos</span>

## 2. Use the right voice, tone, and level of formality

The [Microsoft voice](/style-guide/brand-voice-above-all-simple-human) targets a broad set of users from technology enthusiasts and professionals to casual computer users. Translating the Microsoft voice into Spanish means choosing words and grammatical structures that reflect the same style as the source text. Usually, technical terms are used only in content for technical audiences, but common technology words and phrases can be used in content for consumers, too. In general, the style should be clear and friendly. To that end:
  -	Write short, easy-to-read sentences.
  -	Avoid the passive voice.
  -	Be pleasant and ensure explanations are as clear as is possible.
  -	Avoid slang and be careful with colloquialisms. It is acceptable to reassure and connect with customers in a conversational tone, but be professional in doing so.

**Examples**

_English_: Would you like to continue?

_Our style_: <span lang="es">¿Quieres continuar?</span>

<br>

_English_: Be a presentation machine.

_Our style_: <span lang="es">Conviértete en un experto en presentaciones.</span>

Shorter is always better. Long strings of text can cause issues for localization. Be concise but avoid abbreviations as much as possible because they can make the text less intuitive.

### "<span lang="es-ES">Tú</span>" and "<span lang="es-ES">usted</span>" (informal _vs._ formal)
The way of addressing the user is not uniform across Microsoft products for Spanish. Because different products have different uses and audiences, some have chosen to address the user with the familiar "<span lang="es-ES">tú</span>" and others with the formal (Office, for example). Always consult the Localization project manager if you are not sure about the treatment used in the product.

## 3. Pay attention to application, product, and feature names

Application or product names are often trademarked or may be trademarked in the future and are therefore rarely translated. Occasionally, feature names are trademarked, too (for example, IntelliSense). A [list of Microsoft trademarks](https://www.microsoft.com/en-us/legal/intellectualproperty/trademarks/usage/default.aspx) is available for your reference.

When a product name contains a preposition, the preposition is usually translated. Always consult the product team to find out if a name should be translated.

### Trademarked product name that contains a preposition

**Example**

_English_: Microsoft Visio Pro for Office 365

_Our style_: <span lang="es-ES">Microsoft Visio Pro para Office 365</span>

Visio and Office 365 are Microsoft trademarks; the preposition is translated.

### Descriptive feature names

**Example**

_English_: File Manager

_Our style_: <span lang="es-ES">Administrador de archivos</span>

The feature name is translated because it is descriptive and it is not trademarked.

###	Trademarked feature names

**Example**

_English_: Cortana

_Our style_: <span lang="es-ES">Cortana</span> 

Cortana is not a descriptive feature name and is trademarked.

###	Wizard names

Wizard names should follow the approved format when being translated into Spanish: **<span lang="es-ES">Asistente + para + noun or Asistente + para + infinitive + object</span>**.

**Example**

_English_: Sync Wizard

_Our style_: <span lang="es-ES">Asistente para sincronización</span>

**Example**

_English_: Add Role Wizard

_Our style_: <span lang="es-ES">Asistente para agregar roles</span>

### Versions	

"Version" in the version specification should be translated

**Example**

_English_: MPEG-4 video codec version 1.0

_Our style_: <span lang="es-ES">códec de vídeo MPEG-4 versión 1.0</span>

### All rights reserved

The string "All rights reserved" should be translated, using the approved translation.

## 4. Avoid abbreviations and follow guidelines for acronyms

In running text, avoid abbreviations. If you absolutely need to use an abbreviation, use the form listed in the new Ortografía de la lengua española or in [Appendix 2](http://buscon.rae.es/dpd/apendices/apendice2.html) of <span lang="es-ES">_Diccionario panhispánico de duda_</span>. Remember:
  -	To avoid confusing the reader, do not abbreviate a word in such a way that the abbreviation could be confused with another word.
  -	Include a period at the end of an abbreviation.
  -	Use abbreviations for days and months if necessary. Follow the guidelines in the [main Style Guide](https://www.microsoft.com/en-us/language/StyleGuides?rtc=1) or Regional Standards.
  -	Don't treat words such as "<span lang="es-ES">metro</span>" or "<span lang="es-ES">litro</span>" as abbreviations. They are considered units of measure and should not end in a period. 
  -	Use a nonbreaking space between the numeral and the symbol, as per SI standards. For example: 30&nbsp;cm, 1&nbsp;h, 75&nbsp;%, 20&nbsp;°C.

### Acronyms

Some well-known examples are WYSIWYG (What You See Is What You Get), DNS (Domain Name Server), and HTML (Hypertext Markup Language).
  -	Acronyms behave like nouns. If a gender is needed, it is that of the spelled-out form. In the case of non-Spanish words, the gender will depend on the use.
  -	Acronyms have no plural, so no "–s" is added at the end. The number is indicated by the preceding determiner: <span lang="es-ES">los DVD, unos CD</span>. In the case of PC, the gender should be masculine, "<span lang="es-ES">el PC</span>." When the text refers to PCs and the Mac, please use "<span lang="es-ES">ordenador</span>."

**Localized acronyms**: If the acronym is widely used and well known to the audience, it should be used "as is" (without including the spelled-out term). However, if the acronym is not widely used or could be confused with another acronym, the recommendation is to spell out the term and include the acronym in brackets the first time the acronym appears in the text. Do not include <span lang="es-ES">por sus siglas en inglés</span>.

**Example**

_English_: Uninterruptible power supply (UPS) management

_Our style_: <span lang="es-ES">Administración del sistema de alimentación ininterrumpida (SAI)</span>

Acronyms that aren't localized: When an acronym will remain in English, consider the following.
  -	If the acronym is in common use, it can be used on its own, without being spelled out: for example, CD, DOS, DSL, DVD, ISO, IP
  - If the acronym is not widely used:
     -	The first time it occurs, write its full name in Spanish, followed by the English acronym in parentheses. 
     -	If it's necessary to spell the full name in English the first time the acronym appears to make it clear to the reader, spell the full name in Spanish in regular text, followed in parentheses by the acronym and its full spelling in English in italics. 

**Example**

_English_: This policy setting controls data exchange with other applications that use Dynamic Data Exchange (DDE).

_Our style_: <span lang="es-ES">Esta configuración de directiva controla el intercambio de datos con otras aplicaciones que usan Intercambio dinámico de datos (DDE).</span>

OR

_Our style_: <span lang="es-ES">Esta configuración de directiva controla el intercambio de datos con otras aplicaciones que usan Intercambio dinámico de datos (DDE, Dynamic Data Exchange).</span>

**Note**: For protocol names, file formats, and well-established acronyms, do not add the spelled-out form because the spelled-out form is rarely used.

**Example**

_English_: Graphic Interchange Format (.gif)

_Our style_: <span lang="es-ES">formato GIF</span>

## 5. Use correct capitalization

When localizing Microsoft products, the standard capitalization rules for Spanish should be followed, even for software strings.

For user interface elements, capitalize only the first letter of the first word in commands, dialog box titles, dialog box options, menus, and buttons, as well as the names of panes, views, and windows.

**Example**

_English_: Disable Save As

_Our style_: <span lang="es-ES">Deshabilitar Guardar como</span>

For key names, follow the same character formatting used in the source. 

**Example**

_English_: CTRL+G

_Our style_: <span lang="es-ES">CTRL+G</span>

**Example**

_English_: Ctrl+Shift+A 

_Our style_: <span lang="es-ES">Ctrl+Mayús+A</span>

In headings, captions, and the titles of tables and figures, capitalize only the first letter of the first word, any proper nouns, and any user interface terms that require it.

**Example**

_English_: Quick Reference Guide

_Our style_: <span lang="es-ES">Guía de referencia rápida</span>

## 6. Pay attention to pronouns

For a more fluent text, avoid redundant pronouns in a sentence. In Spanish, omitting some pronouns when the meaning is clear from the context makes the text sound more natural.

**Example**

_English_: Depending on your service agreement, you might pay more for call or text messages when your phone is roaming.

_Our style_: <span lang="es-ES">Según el contrato de servicio, tal vez tengas que pagar más por llamadas o mensajes de texto cuando el teléfono esté en roaming.</span>

Remember that the form for the second-person plural in Spanish for Spain is "<span lang="es-ES">vosotros</span>" and not "<span lang="es-ES">ustedes</span>." If possible, use an alternative construction to avoid one or the other.

**Example**

_English_: Many of you are, for sure, familiar with Microsoft webcast

_Our style_: <span lang="es-ES">Seguro que muchos ya conocen los webcast de Microsoft</span>

_Not our style_: <span lang="es-ES">Seguro que muchos de ustedes conocen los webcast de Microsoft</span>

Check the correct use of _<span lang="es-ES">leísmo</span>_. Please make sure that the use of "<span lang="es-ES">le</span>" is grammatically correct when used instead of "<span lang="es-ES">lo</span>."

**Example**

_English_: This wizard will help you …

_Our style_: <span lang="es-ES">Este asistente le ayudará a …</span>

## 7. Use simple tenses

Simple tenses are preferred to compound tenses.

**Example**

_English_: After you have finished installing the tool, the icon appears on the desktop.

_Our style_: <span lang="es-ES">Después de que termines de instalar la herramienta, aparecerá el icono en el escritorio.</span>

OR

_Our style_: <span lang="es-ES">Después de que instales la herramienta, aparecerá el icono en el escritorio.</span>

**Note on the subjunctive mode**: Do not avoid using the subjunctive. The subjunctive mode makes the text richer and more natural sounding. 

The only point to remember is that, when either "<span lang="es-ES">cantara</span>" or "<span lang="es-ES">cantase</span>" could be used, the second option is more common in Spain, so use "<span lang="es-ES">cantase</span>" instead.

## 8. Use Microsoft style for punctuation

In general, follow the standard punctuation rules used in Spanish. However, to promote a consistent style within Microsoft products, follow these guidelines:

  -	UI strings: Use final periods as they are used in the source text because we cannot foresee how the strings will combine or concatenate at runtime.
  -	Bulleted lists:
    -	Items that are composed of full sentences have a period at the end. 
    -	Items that are not composed of full sentences have no period.
  -	Comma: Do not copy the use of commas in the English source text; follow Spanish grammar. 

**Example**

_English_: Sync your mail, contacts, calendar, and tasks

_Our style_: <span lang="es-ES">Sincronizar tus emails, contactos, calendarios y tareas</span>

## 9. Be consistent when translating error messages

### Voice and tone

Translators should apply the Microsoft voice principles to ensure that the translation sounds natural and empathetic, not robot-like.

**Example**

_English_: Oops, that can't be blank …

_Our style_: <span lang="es-ES">¡Uy! Esto no puede estar en blanco…</span>

###	Spanish style in error messages

Use consistent terminology and language style in the localized error messages. Do not just copy what appears in the US product. Do not transfer exclamation points used in the English source text to the Spanish translation.

**Example**

_English_: Operation failed!

_Our style_: <span lang="es-ES">No se pudo realizar la operación.</span>

### Syntax and punctuation

Error messages are made of two parts: the issue and the action that the user needs to take or follow. The English text can separate those two elements with a period, a semicolon, or a colon. In Spanish, we always use **a period as the separator.**

In short sentences with the verb "to be," the nominal form is favored for conciseness.

**Example**

_English_: The disk is full. You cannot save this file.

_Our style_: <span lang="es-ES">Disco lleno. No se puede guardar el archivo.</span>

In long sentences with many participles, the verbal structure is preferred. 

**Example**

_English_: An error number was specified that is not defined in the system.

_Our style_: <span lang="es-ES">El número de error especificado no está definido en el sistema.</span>

### Standard phrases in error messages

**Example**

_English_: Cannot … / Could not … / Unable to …

_Our style_: <span lang="es-ES">No se puede…</span>

**Note**: The English forms above should always be translated as "<span lang="es-ES">No se puede</span> + infinitive." For messages that contain "could not," if it is important to convey that the action occurred in the past, "<span lang="es-ES">No se pudo</span>" should be used.

**Example**

_English_: Failed to … / Failure of …

_Our style_: <span lang="es-ES">Error… → Error en la conexión</span> 

**Note**: Translate messages that end with "failed" or start with "Failure" or "Failed to" as "Error + preposition." Avoid using <span lang="es-ES">fallo/falló</span>.

**Example**

When "failed to" appears in the middle of the sentence, with a subject and a complement, follow this construction: "subject + <span lang="es-ES">no se pudo + complement.</span>"

_English_: Setup failed to initialize.

_Our style_: <span lang="es-ES">La instalación no se pudo inicializar.</span>

**Example**

_English_: … occurred / … has occurred

_Our style_: <span lang="es-ES">Error… → Error de escritura / Error durante la reconexión de %2 a %3.</span>

**Note**: Omit the translation for "occurred" or "has occurred" in error messages like "A write fault occurred" or "An error occurred while reconnecting %2 to %3" and whenever possible. Do not use _<span lang="es-ES">ha ocurrido</span>_ or _<span lang="es-ES">ocurrió</span>_.

**Example**

_English_: Not enough memory / Insufficient memory / There is not enough memory.

_Our style_: <span lang="es-ES">Memoria insuficiente.</span>

**Note**: Even though there are several valid ways to convey this idea, this translation is preferable so that the translated error messages are concise and consistent.

**Example**

_English_:  … not found.

_Our style_: <span lang="es-ES">No se encuentra → No se encuentra el archivo.</span>

**Note**: Use this form for messages such as "File not found" or "Value not found in Configuration Registry."

### Error messages that contain placeholders

When localizing error messages that contain placeholders, find out what will replace the placeholder. Note that the letters used in placeholders convey a specific meaning. 

  - %d, %ld, %u, and %lu means &lt;number&gt;
  - %c means &lt;letter&gt;
  - %s means &lt;string&gt;

**Examples**

  - "Checking Web %1!d! of %2!d!" means "Checking Web &lt;number&gt; of &lt;number&gt;".
  - "INI file "%1!-.200s!" section" means "INI file "&lt;string&gt;" section".

Consider the meaning of the placeholder when translating strings, and move the placeholder into the appropriate position to comply with the rules of the language.

## 10. Use the following reference material

Use the spelling and grammar recommended in the following publications.

These normative sources must be adhered to. When more than one solution is possible, consult the topics in the [Spanish (Spain) Style Guide](https://www.microsoft.com/en-us/Language/StyleGuides) for guidance.

1.	_Diccionario de la lengua española_, (Vigésima tercera edición), Real Academia Española, Madrid, Ed. Espasa-Calpe, 2014, or [online](http://www.rae.es/).
2.	_Diccionario panhispánico de dudas_, Real Academia Española & Asociación de Academias de la Lengua Española, Madrid, Ed. Santillana, 2005 or [online](http://www.rae.es/recursos/diccionarios/dpd).
3.	_Gramática de la lengua española_, Real Academia Española y Asociación de Academias de la Lengua Española, Madrid, Ed. Espasa-Calpe, 2009. Queries [online](http://aplica.rae.es/grweb/cgi-bin/buscar.cgi).
4.	_Ortografía de la lengua española_, Academias de la Lengua Española, Ed. Espasa, 2010. Queries [online](http://aplica.rae.es/grweb/cgi-bin/buscar.cgi).

These sources are meant to provide supplementary and background information.
1.	_Diccionario de uso del español_, Moliner, M., Madrid, Ed. GredosS.A., 1991
2.	_Diccionario de informática_ (2.ª ed.), Oxford University Press, Ed. Díaz de Santos, 1992
3.	_Diccionario comentado de terminología informática_, Aguado de Cea, Ed. Paraninfo, 1996
4.	_Microsoft Diccionario de Informática e Internet_, McGraw-Hill Interamericana, Madrid , 2001
5.	_El lenguaje de la informática e Internet y su traducción_, Belda Medina, J.R., Publicaciones de la Universidad de Alicante, 2003
6.	[Diccionario de Internet ATI](http://www.ati.es/novatica/glointv2.html) 
7.	[Fundeu](http://www.fundeu.es/)
8.	[Wikilengua del español](http://www.wikilengua.org/index.php/Portada)
