---
title: Personal names and postal address formats
description: Understand the conventions for personal names and postal addresses for international markets.
ms.date: 06/13/2023
---

# Personal names and postal address formats

A common issue for internationalizing products that were initially created for a United States market is collecting and displaying users’ names and postal addresses. Name order in the United States is typically given name (first name), middle name, then family name (last name, surname). United States postal addresses generally follow a format of:

{Recipient name}<br/>
{Street address, number followed by street name}<br/>
{City}, {State} {ZIP+4 code}

For customers in markets other than the United States, you shouldn't assume that name order or address format follows the United States conventions.

## Personal names and name order

Components of personal names can include:

- One or more given names.
- One or more family names.
  - In some countries/regions, a person’s full name includes both the mother’s and father’s family names. Typically, the last family name is used for a shortened version of a personal name.
  - Names for some Eastern European languages should be declined, so a male might have the family name Ivanov (Иванов), while a female might have the equivalent name Ivanova (Иванова).
- A patronymic name.
- A matronymic name.

Name order can also vary by culture. While given name - family name is common in Western cultures, family name – given name is common in Eastern cultures. Name order might vary depending on the script used to write the name.

When designing an interface to collect personal names and the data storage for the information, you should consider whether to have separate fields for family and given names, or one field for the entire name. A single name field allows the user to specify how they would like their name to appear; however, using separate name fields allows the developer to use different levels of formality (for example, using only the user’s first name or referring to the user as Mr. Smith) when communicating with the user. If you choose to use multiple fields, you should ensure that the name order is correct for the target market, both when collecting the data and when addressing the user.

When referring to the user, the level of formality should reflect the expectations of the target market. While it might be appropriate to use a given name for customers in the United States, using only a person’s given name might be considered rude in other markets.

For some languages, you might want to consider enabling the user to supply the pronunciation of their name. For example, Japanese names written in Kanji can have several pronunciations.

## Postal address

Like name order, the number of components of an address and the conventional display order vary by country or region. In general, postal addresses start with the recipient’s name and end with the largest geographical unit, or vice versa. Geographical units can include:

- A country name.
- A major administrative division, such as a state, province, or oblast.
- A locality, such as a city, town, or village.
- A minor administrative division, such as a city area or district.
- A street name.
- A street number or house name.
- A postal code (ZIP code).

Every country/region has required or recommended standards for postal addresses. These standards include the order of the information, the separators used between each geographical unit, and which information can be combined on each line of the address.

For each target market:

- When designing an interface, consider which fields are needed to accurately capture the user’s address. Ensure that the order in which the fields are displayed is appropriate for the market. Ensure that the geographical units are named correctly.
- If you're validating the address that a user has entered, ensure that it's valid for the recipient’s location.
- When printing the address for use with the postal service, ensure that the address format meets the requirements of the market. The correct address format might also depend on the script used to display the address. For example, if a Japanese address is written in Kanji, the correct order is postal code, address (from larger to smaller unit), recipient. However, if the Japanese address is written in Romaji, the correct order is recipient, address (from smaller to larger unit), postal code.

As there's no international standard for address formats, determining the appropriate postal address format can be challenging. Libraries like ICU, frameworks like .NET, and programming languages like Java don't provide features to facilitate address storage or formatting. The best reference sites are the sites for the postal service in each country/region; however, the Universal Postal Union has published the [POST*CODE® DataBase](https://www.upu.int/en/Postal-Solutions/Programmes-Services/Addressing-Solutions), which can be used to validate addresses worldwide.
