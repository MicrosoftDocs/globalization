---
title: Global product delivery
description: A great global product has a rich experience that feels like it was created specifically for you, no matter where you live or the language you speak.
---

# Global product delivery

> If you talk to a man in a language he understands, that goes to his head.
> If you talk to him in his language, that goes to his heart.
>
> &#x2014; Nelson Mandela

A great global product has an experience that goes beyond the basic function of the product.
As a customer, the product feels like it was created specifically for you, no matter where you live or the language you speak.
It feels like it belongs to your culture, language, and region.

When you get global readiness right,
you create opportunities for your company by ensuring your products and content are globally acceptable and locally compelling.

We all want to do the right thing for our customers.
That includes being respectful of the diversity of local laws and cultures
and being relevant in each market.

## Market and cultural awareness

When planning, be intentional and specific about the scope of your audience by country, region, and language.

Know your markets and audiences to be more relevant to your customers.
We all come with an intuitive sense of what is acceptable and expected based on our own cultural and regional experience.
The experiences of people elsewhere in the world can be remarkably different.
Stereotypical, inauthentic, or lack of diverse representation can turn customers away.

Consider these aspects, that may vary widely by locale and language:

* Access to technology and bandwidth.
* Payment methods.
* Familiarity with computers and technology.
* Phones may be the primary technology, with few desktops or laptops available.
* Personal computer ownership may be low. Computers may be shared at work or in internet cafes. A family may share a single computer.
* In some regions, the majority speaks only one language. In other regions, most users speak two or more languages.

When you get to specifics in your application, keep in mind significant locale differences in:

* Language and language variants, including word choice, spelling, and punctuation
* Reading order and text layout
* Typographical conventions
* People's names
* Calendars
* Date and time formats
* Number formats
* Currency unit and formatting of monetary values
* Postal addresses
* Telephone numbers
* Measurement units
* Paper sizes

To delve into the details of these considerations (and much more), see [International design](international-design.md).

## Localization strategy for different types of content

There isn't a universal way to do localization.
The type of content or software you're creating will drive varying strategies.
See:

* [Localize software](../localization/localize-software.md)
* [Localize content](../localization/localize-content.md)
* [Localize games](../localization/localize-games.md)

## Regulations

To avoid surprises when you release your product, research the legal and regulatory requirements for each locale.
Your product may need to be registered with local authorities, and such paperwork may be required to be in a specific language.
Your product may need to conform to local language laws, providing content or user interface in specific languages.
Privacy considerations are increasingly regulated in many parts of the world.
Certain features may be regulated or restricted, particularly encryption and anti-malware features.

## Roles

Delivering software products worldwide can be a complex process that involves many disciplines within an organization.
Global product delivery can require awareness and participation from:

* Development
* Content creation
* Legal affairs
* Marketing
* Operations
* Procurement
* Finance
* Sales and support

See [Roles and responsibilities](roles-and-responsibilities.md)

## Start early

When you build global awareness and localizability into your product and process as early as possible, you reduce risk and cost.

In our experience, world-readiness can be quite challenging to retrofit to an existing application.
For a pre-existing application, many components may need to be redesigned, particularly in the user interface.

Even if your initial release is in only one language, a world-ready application can reach more markets.
When you're ready to localize into to more languages and markets, the cost is lower because your organization and the application are prepared.

## <a name="baseline"></a>Minimum baseline for localizability

When starting a project, it's vital to get these fundamentals in place as early as possible:

1. [Externalize resources](../internationalization/externalize-resources.md), separating localizable from non-localizable resources.

2. Produce and test localized builds.

   [Pseudolocalization](pseudolocalization.md) is an excellent strategy to enable build and test without the cost of translation.

3. Validate the localization round-trip from development to translator and back.

   Perform an early pilot, perhaps with minimal content and only one or a few languages, to minimize surprises later.

4. Implement the ability to choose the language and locale.

   Having a means to select the language and locale independently from the language and locale of the platform makes it easy to develop, test, and debug with a minimum of friction.
   Plus, it's a useful feature for users.

This baseline should be maintained for the entire lifecycle of the product.

Once you've set a strong baseline, you can start iterating.
For each sprint or milestone, evaluate your status and progress by defining [exit criteria](exit-criteria.md).

For next steps, see [Global products and rapid development](rapid-development.md).
