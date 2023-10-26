---
title: Proofing tools
description: Dictionaries, spelling algorithms, and other proofing tools require special treatment in a global application.
author: m-kauppinen
ms.author: v-mikau
ms.topic: conceptual #Required; leave this attribute/value as-is.
ms.date: 10/25/2023

---

# Proofing tools

Your product might come with or incorporate proofing tools if it allows users to enter text. These tools can include the following:

- Spelling
- Autocorrection/Autocompletion
- Hyphenation
- Grammar
- Thesaurus
- Readability analysis
- Style and tone analysis
- Plagiarism analysis
- Word counting
- Accessibility analysis

If your product includes proofing tools, they should be available for all languages that the product supports. For example, if you’re using a spellchecking library, you need to check if the library supports all your target languages. If that’s not the case, you’ll need to think how to handle unsupported languages (refer to [Locale fallback](fallback.md) for a similar situation).

If you aren’t developing your own proofing tools, you should ensure that the libraries that you are using support the languages that you need. When selecting a vendor for proofing tools, ensure that the tools support all the languages that you need, or are willing to develop support for missing languages.

If your implementation uses features like custom dictionaries you need to ensure that features of supported languages can be correctly handled. For example, to support inflection in Slavic languages, you should not need to store all possible declensions of a word added to the custom dictionary.
