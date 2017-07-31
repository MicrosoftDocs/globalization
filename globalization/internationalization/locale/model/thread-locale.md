This documentation is archived and is not being maintained.

# Thread Locale

The thread locale defaults to the currently selected user locale and determines the formatting of dates, times, currency, and large numbers for the thread. It can be changed programmatically using the API SetThreadLocale, but in most cases the thread locale should not be overwritten.

On Microsoft Windows NT 4.0, many applications used the thread locale to define which language resources should be retrieved and displayed. However, this practice represents a misusage of the thread locale. (In Windows 2000 and Windows XP, the system's resource loader does not default to the thread locale variable.) As you'll see, resource languages should always be driven by and follow the user interface (UI) language variable.

[Show:]{} Inherited Protected
