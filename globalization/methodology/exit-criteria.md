---
title: Localization exit criteria
description: Every development milestone should have a set of indicators for key areas to ensure quality. This article suggests ways of defining localization exit criteria for these milestones.
---

# Localization exit criteria

Every development milestone, short or long, Agile or waterfall, should have a set of key metrics to ensure the quality of a deliverable.
Some of the areas typically covered by a metric are security, privacy, accessibility, reliability, and performance.
Internationalization should also be included as one of these key areas.

Your "international" metric might be called "globalization", "localization", "international", or "world-readiness".
Use whatever term is understood and meaningful for your organization.

An international exit criteria should be created even if your release is only targeting English as a language.
A global-ready application has more market opportunities because English is widely understood.

World readiness involves several layers of product development.
Areas include user research, architectural and design considerations, programming (coding), localizability, and legal compliance requirements.
Although the delivery of such requirements can be prioritized and staggered across several sprints, some requirements have strong downstream dependencies.
If foundational aspects aren't addressed from the very beginning, trying to incorporate them in later sprints could prove to be costly.
Redesign and refactoring efforts are required in some cases, which can be more expensive to incorporate later.

Some of the aspects that you should include in your exit criteria:

- Separation of localizable resources

- Text handling and display support

- String authoring

- Language and location selection

- User interface and layout

Such aspects are validated through testing.
For more information about testing and validation:

- [Global test design](../testing/globalization-of-the-test.md)
- [Localizability testing](../testing/localizability-testing.md)
- [Localization testing](../testing/localization-testing.md)
- [Test case samples](../testing/sample-international-test-cases.md)
