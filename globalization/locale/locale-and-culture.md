

# Locale and Culture Awareness

[](https://msdn.microsoft.com/en-us/library/mt662310)
## Using Locale Model

To represent the data (number, currency, etc.) correctly, the software needs to be aware of the user's locale. To create software that is locale and culture aware, you'll need to understand what the term "locale" means, as well as the role locale variables play in the development process.

[](https://msdn.microsoft.com/en-us/library/mt662313)
## Sorting and String Comparison

String sorting and comparison are language-specific. Even within languages based on the Latin script, there are different composition and sorting rules. Thus do not rely on code points to do proper sorting and string comparison.

[](https://msdn.microsoft.com/en-us/library/mt662317)
## Calendar Differences

The Gregorian calendar is used in most English speaking countries, but world-ready products should also take into consideration other calendaring systems in use worldwide.

[](https://msdn.microsoft.com/en-us/library/mt662320)
## Date Formatting

Date formatting is not constant through out the world. Although each date basically displays the day, month, and year, their presentation order and separators vary greatly. In fact, there may be many differences between regions within the same country.

[](https://msdn.microsoft.com/en-us/library/mt662321)
## Time Formatting

Like date and calendar formats, time formats are not constant throughout the world.

[](https://msdn.microsoft.com/en-us/library/mt662322)
## Currency Formatting

Currency formatting needs to take into consideration the currency symbol and symbol placement, and the number formatting display.

[](https://msdn.microsoft.com/en-us/library/mt662324)
## Number Formatting

The number formatting deals with the character used as the decimal and thousands separators.

[](https://msdn.microsoft.com/en-us/library/mt662325)
## Addresses

Various countries/regions have different address formats.

[](https://msdn.microsoft.com/en-us/library/mt662326)
## Telephone Number

Like addresses, the format for telephone numbers around the world varies significantly. The input fields and the routines that process information dealing with telephone numbers should be able to handle the variety of formats.

[](https://msdn.microsoft.com/en-us/library/mt662327)
## Paper Size

It's important to set the paper size correctly if your application supports the print function.

[](https://msdn.microsoft.com/en-us/library/mt662328)
## Units of Measurement

Throughout the world things are measured using different units and scales. The most popular one used is the metric system (meters, liters, grams, etc). Where as the US still uses the imperial system (feet, inches, pounds, etc).


