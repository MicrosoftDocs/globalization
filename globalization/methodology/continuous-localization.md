---
title:  Continuous localization
description: A faster cadence of development and release requires continuous delivery of localized content.
--- 

# Continuous localization

A rapid development model uses continuous integration (CI) and continuous delivery (CD) to make fast iteration possible.
The same benefits accrue when you also use continuous localization.
With continuous localization, new and updated strings are handed off as soon as they're available.

In a classic development model, localization handoffs happen at the end of a major milestone, such as "visual freeze".
These handoffs can be large and may take a long time to be translated and handed back.
After the translations are integrated into the product, a large testing effort follows.
Infrequent handoff introduces large peaks in the effort and resources required to integrate and test.
Taking infrequent snapshots for hand-off doesn't fit a rapid development model.

With short development sprints delivering complete features, your localization model should follow a similar strategy.

Continuous localization handoffs are small.
They can be turned around quickly, ideally within the same sprint.
Many localization service providers can turn around a considerable volume in just a few hours.

There can be more "churn" under this model as source strings are updated, added, and removed.
Your intuition may say that this increases translation cost because you're translating a greater volume over time.
However, the cost isn't as large as you might expect.

* Many strings are automatically "recycled" by finding matches in the translation memory.
  High-confidence matches are typically no-cost.
  Low-confidence or "fuzzy" matches are often charged a reduced rate, because they require only review and not full translation.

* Small updates to a string, such as changing punctuation or correcting a typographical error are commonly charged at a lower rate.

With continuous localization, translated versions of the product are available at the same time as the source version and can be tested at the same time.
Testing is focused on just the features delivered in the sprint, just as with the source version of the product.
The localization test load is thereby spread over the product lifecycle, instead of concentrated on a few major milestones.

Continuous localization is even more efficient when there's a tight integration with your development system.
A service provider may have APIs or tools that create a direct connection between your development system and the provider's translation management system.
An integrated system connection avoids an error-prone manual process of transferring and integrating localization files.
At Microsoft, many teams use a system where resource localization happens directly during the primary build process.

Continuous localization may demand adjustments to the business model and service agreements with localization suppliers.
