

# Locale Data and Character Sets

Formats of dates, time, currency, measurements, and telephone numbers vary from one locale to another. Again, localizing the software to suit an international audience requires using the appropriate format for the particular locale. You can change a format programmatically by using the globalization infrastructure provided in Windows operating systems and the .NET Framework. (For more information, see [[Use Locale Model]](https://msdn.microsoft.com/en-us/goglobal/bb688121 "Use Locale Model").) Some instances of locale-data values can be stored as part of the resources to initialize variables like the default character set or the default date format. If the development team does indeed want to store these values, localizers should change the locale-value strings according to the format of the target locale.


