---
title: Parsing input
description: Learn how the context and the locale are crucial when parsing user input
ms.date: 1/24/2024
author: jowilco
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-desc
  - ai-seo-date:01/24/2024
---

# Parsing input

Users can input data into applications, for example, directly in text boxes or uploading data files. If there isn't an explicit way to indicate the locale for the data, each application must make assumptions about the implicit locale of the data. For example, if a user inputs numeric data in Germany, the application might assume that a comma indicates a decimal separator. If the same data was inputted in the US, the application might assume that a comma indicates a grouping (thousands) separator. Furthermore, the application might need to collect numerical data from users in Germany and display the data to users in the US, using the correct grouping and decimal separation in each context.

As with formatting numbers and formatting dates, libraries like ICU, frameworks like .NET, and programming languages like Java have methods that can assist with parsing and storing user input.

In general, it's best practice to assume that numbers, dates, and times are entered in a format that corresponds to a format supported by the current application locale. There are occasions where you might want to parse numbers, dates, and times with alternative locales. For example, an application that extracts numeric data from documents might be running with a locale setting of French (France), but the user has indicated that a document has a locale of German (Germany). In this context, using the locale of the document might be more appropriate when parsing the numeric data.

Locales specify the decimal and grouping separator used to format numbers. Windows allows users to select the list separator, which can also be used as the default delimiter for applications to support formats like CSV. While CSV can support a delimiter that is the same as either the grouping or decimal separator, using a delimiter that is different than either the grouping or decimal separator is more common. Applications need to determine the locale, and consequently the separators and delimiters used when trying to read CSV data.

There are extra concerns when parsing and storing dates and times. For example, a scheduling application might allow users in different countries or regions to schedule meetings together. It's best practice to convert the local date and time to a fully specified date and time (see ISO 8601), including time zone, so that you can ensure that dates and times can be converted correctly to display to users in different countries and regions.
