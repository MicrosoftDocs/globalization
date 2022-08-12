---
title: Roles and responsibilities
description: All members of a product team have roles and responsibilities with respect to globalization and localization. This article describes a role framework to help understand the work to be done.
author: v-pdempsey
ms.date: 6/7/2022
---

# Roles and responsibilities

As with all aspects of product development, a role framework is useful for understanding the work to be done for localization.
A large organization may have specialists that fulfill each of these specific roles.
In a small organization, individuals may cover more of the roles described here.

Not everyone needs to be an expert, but everyone should have some awareness of internationalization basics.
In a larger team, you can use the "champion" concept: individuals become champions for a particular area and develop expertise.
The champion is the local expert in a subject, acting as a resource for the rest of the team.
To develop depth in a team, trade off the champion role over time.
Each champion steps back from a front line role and mentors the next champion.

## Source roles

The roles and responsibilities at source set the stage for doing actual localization:

* architect
* designer
* developer
* content creator
* product/program manager (strategy and product design)
* user experience designer
* project management (tracking and scheduling)

## Localization roles

These are the roles involved in the actual localization process:

* localization tools development
* tester
* translator
* local content creator
* language validator
* project manager (translation coordination)

The timing for engaging in the activities for each role is critical.
If world-readiness isn't considered at each step, the ability to create localized versions is at risk and fixing it is expensive.
The risk is highest when the [fundamental baseline](global-product-delivery.md#baseline) is missing.

## Responsibilities

Another perspective is to examine the activities that each role is responsible for.

Managerial activities include:

* Design global features.
* Define [exit criteria](exit-criteria.md) to measure international status and progress.
* Define visual style guides, including mirroring.
* Define content style guides, covering terminology and usage. Style guides are consumed by both developers and translators.
* Establish issue tracking for the localization process and locale-specific issues.
* Schedule alignments between development and the translation provider.

Technical activities include:

* Enable localization:
  * Externalize localizable resources
  * Comment resources
  * Create the translation pipeline
  * Create localized builds
* Implement language and region detection and user selection
* Employ globalization APIs
* Validate localizability
* Validate (test) functionality
