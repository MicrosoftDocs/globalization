---
title: When to perform internationalization testing
description: Using appropriate testing methods at the right time helps identify bugs before rework increases expense.
author: m-kauppinen
ms.author: v-mikau
ms.topic: conceptual #Required; leave this attribute/value as-is.
ms.date: 05/04/2024

---

# When to perform internationalization testing

Releasing a product internationally involves more testing than you might realize. Developers know that each localized version needs to be tested, but there are also things you can do before getting to that stage. This "prelocalization testing," also known as internationalization testing, aims to validate your code is properly internationalized.

The purpose of internationalization testing is to verify that the user interface of the app can be easily translated to any target language without re-engineering or making code modifications. Since internationalization bugs must be fixed in the code, they should be found as early during development as possible. This saves time later, as you don’t need to find and fix the same bugs for each target language. After localization has been carried out, the results are then checked in [localization testing](how-to-perform-localization-testing.md).

However, some bugs and other issues may become more apparent after translations has been completed. The goal is to minimize the number and severity of issues found after translation, to reduce late rework, but is typically not a full substitute for validating localized versions.

There are four things you can do to reduce the impact of this fundamental problem.

1. Long before any translation work is done, you can [review your code](how-to-perform-internationalization-testing.md#review-your-code).
1. Closer to the start of localiation, [review the source language UI and documentation](how-to-perform-internationalization-testing.md#review-the-source-language-ui-and-documentation).
1. Before starting localization, you can also [test with a pseudolocalized version of your app](how-to-perform-internationalization-testing.md#test-with-a-pseudolocalized-version-of-your-app). If your product supports right-to-left scripts, also test with a pseudomirrored version.
1. [Start localization with a small set of languages](how-to-perform-internationalization-testing.md#start-localization-with-a-small-set-of-languages).

The four stages are described in detail in [How to perform internationalization testing](how-to-perform-internationalization-testing.md).
