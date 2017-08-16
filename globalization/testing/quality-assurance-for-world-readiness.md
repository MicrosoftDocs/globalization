---
title: Quality Assurance for World-Readiness
description: The goal of ensuring world-readiness has a wider scope and requires more fore-thought than merely testing localized applications.
ms.assetid: 6ba1dbde-55ae-4495-be7f-03473e2aca30
ms.date: 04/03/2017
---

# Quality Assurance for World-Readiness

The goal of ensuring world-readiness has a wider scope and requires more fore-thought than merely testing localized applications. It must start early on by determining the necessary criteria for globalization and hence world-readiness. Then the QA organization must make sure that those implicit requirements are met throughout the design and development steps.

For software products shipped to multiple markets, the single, world-ready binary dramatically simplifies the QA process. Indeed, before software globalization, the development process entailed concurrent development of essentially different products-language-specific binaries-to ensure they all had matching functionality. By using a single, world-ready binary, however, you only have to deal with one product built for one specification, one development team, and one binary that can be tested, tracked, and supported later on. In addition, expanding the target market of the product becomes easier and more efficient, since you do not need to retest the single, world-ready binary completely to sell it in another country.

You can achieve all these benefits if the application you build targets a world-ready platform, such as Microsoft Windows. However, just because a platform is world-ready does not necessarily mean that an application's code is automatically globalized. Software design and development can easily break world-readiness when:

-   Legacy, single-language methods and practices are used.
-   Local conventions are not considered.
-   Text layout and other properties are not designed for.

Making software world-ready is a new goal for many software companies, and problems are likely to arise when new technologies and methods are applied. The QA organization, especially those responsible for testing, must recognize the problem with test processes that are not world-ready-as shown in the next section-and must be prepared to prevent those problems or reduce their negative effect through proven solutions. (See "[Globalization of the Test](globalization-of-the-test.md)".)


