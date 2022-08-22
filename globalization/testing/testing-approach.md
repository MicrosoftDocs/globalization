---
title: Globalization testing approach
description: Whenever a piece of code handles text or deals with locale-sensitive functionality, it has to be tested for proper functionality from the perspective of world-readiness.
author: PaulDempsey-ms
ms.date: 6/7/2022
---

# Globalization testing approach

In order to help you verify that a product's functionality has been globalized, some central ideas of globalization are restated here.
Among these ideas, an application or a component is considered globalized if:

* It's Unicode-based. Any Unicode text can be handled successfully.

* Correct encodings are selected for text conversions, if conversion is needed to interact with legacy systems.

* The code follows the user's culture-specific settings.

Whenever a piece of code handles text or deals with locale-sensitive functionality, it has to be tested for proper functionality from the perspective of world-readiness.
Code that has been globalized can process data (text) in multiple scripts and can adjust itself to the environment (in terms of language settings, for instance).
Verifying functionality can be planned as a separate test pass, but it's better to fit it into regular functional testing.

Practical guidelines for globalization of your test go beyond breaking any code-page dependency in the test data and checking that the application honors the user's language settings.
To make testing more effective in discovering globalization bugs, target specific functionality and create an environment where this functionality is likely to break.
Here are some of the areas of functionality that testers should verify:

* Input, store, process, and output multilingual text with no data loss.

* Display user interface elements so script properties are respected, including mirroring and text rendering.

* Proper handling of language settings such as date, time, number and currency formatting, calendar and sorting settings.

You've seen the importance of globalizing your test and particular areas of functionality in which to search for globalization bugs.
Before testing is performed, there are several items to consider in preparation.
You'll need to determine [priority for components that are going to be tested](prioritize-components.md), [choose a test platform](choose-a-test-platform.md), and [create a proper testing environment](create-the-test-environment.md).
