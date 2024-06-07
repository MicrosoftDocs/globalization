---
title: Localization exit criteria
description: Every development milestone should have a set of indicators for key areas to ensure quality. This article suggests ways of defining localization exit criteria for these milestones.
author: PaulDempsey-ms
ms.date: 6/7/2022
---

# Localization exit criteria

Every development milestone, whether it's a sprint or a major checkpoint, should have a set of key metrics to ensure the quality of a deliverable.
Key areas covered by a metric include:

* Accessibility
* Internationalization
* Performance
* Privacy
* Reliability
* Security
* Stability
* Usability

Internationalization should also be included as one of these key metrics.
The exit criteria for a milestone is a collection of these metrics, each with a minimum threshold.
Taken together, the exit criteria tell you the status of a project and answer the question "are we there yet?"

Your "Internationalization" metric might be called "globalization", "localization", "international", or "world-readiness".
Use whatever term is understood and meaningful for your organization.

An international exit criteria should be created even if your release is only targeting English as a language.

Internationalization involves several layers of product development.
Areas include user research, architectural and design considerations, programming (coding), localizability, and legal compliance requirements.
Although the delivery of such requirements can be prioritized and staggered across several sprints, some requirements have strong downstream dependencies.
If foundational aspects aren't addressed from the very beginning, trying to incorporate them in later sprints could prove to be costly.
Redesign and refactoring efforts are required in some cases, which can be more expensive to incorporate later.

Some of the aspects that you should include in your "international" exit criteria:

* Localizability
* Separation of localizable resources
* String authoring, including resource commenting
* Text handling and display support
* Language and location selection
* User interface and layout

Such aspects are validated through testing.
For more information about testing and validation, see:

* [Why international validation is important](../testing/why-international-validation-is-important.md)
* [How to perform internationalization testing](../testing/how-to-perform-internationalization-testing.md)
* [How to perform localization testing](../testing/how-to-perform-localization-testing.md)
