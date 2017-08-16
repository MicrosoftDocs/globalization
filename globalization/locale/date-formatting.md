---
title: Date Formatting
description: Each date displays the day, month, and year, but the presentation order and separators can vary in different countries/regions.
ms.assetid: 05632b68-e221-4d77-a85b-68f9d3781ecf
ms.date: 01/24/2017
---
# Date Formatting

Date formatting is not constant through out the world. Although each date basically displays the day, month, and year, their presentation order and separators vary greatly. In fact, there may be many differences between regions within the same country.

To help illustrate this, let's look at two basic date formats:

Long Date (Tuesday, October 12, 1954)  
Short Date (10/12/54)

Now let's compare these formats between United States (English), Mexico (Spanish), and Japan (Japanese).

### Long Date

United States: Tuesday, October 12, 1954  
Mexico: martes 12 de octubre de 1954  
Japan: 1954年10月12日

Obviously, the names of the months and days of the week are different from locale to locale. However, there are other notable differences as well. For Mexico, the day comes before the month, everything is lowercase and the article "de" has been added. In Japan, the day of the week is not displayed, and the translations for day, month and year act more like separators.

### Short Date

United States: 10/12/54  
Mexico: 12/10/54  
Japan: 54/10/12  

In the short date, we again see that in the Mexican example the order is day/month/year as compared to the United States where it is month/day/year. In Japan, the order is year/month/day. This can cause confusion if not watched carefully. For example, depending on which location you are in, the date specified as ***07/04/01*** could mean:

United States: July 4th, 2001  
Mexico: April 7th, 2001  
Japan: April 1st, 2007

These examples shows why you should use the date APIs when dealing with dates. Not only will they handle the correct format, but they will also display the correct translations for the long dates, thus saving translation costs.


