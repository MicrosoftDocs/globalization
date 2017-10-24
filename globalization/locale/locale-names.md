

# Locale Names and LCID Deprecation

In the modern and managed worlds developers have been using Locale Names (a.k.a., [IETF language tags,](http://en.wikipedia.org/wiki/IETF_language_tag) locale tags, language tags, culture tags, culture codes, [BCP 47](https://tools.ietf.org/html/bcp47) tags, ll-cc, “en-US”, et cetera) for some time, but in other contexts LCIDs continue to be used. For those developers still using LCIDs, it is recommended to move to local names as they are more robust than LCIDs and can support many more markets.

### What is a Locale?

A locale is a collection of features of the user’s environment that is dependent on language, country/region, and cultural conventions. The locale determines conventions such as sort order; keyboard layout; and date, time, number and currency formats.

### What is an LCID?

Up until Windows 8, each [locale](https://msdn.microsoft.com/en-us/library/dd318716(VS.85).aspx) supported by Windows had a unique [LCID](https://msdn.microsoft.com/en-us/library/dd373763(v=vs.85).aspx) identifier, a 32-bit value that consists of a [language identifier](https://msdn.microsoft.com/en-us/library/dd318691(VS.85).aspx) and a [sort order identifier](https://msdn.microsoft.com/en-us/library/dd374060(VS.85).aspx). The locale identifier (LCID) is a Microsoft-proprietary numeric identifier for the locale, and before Windows 8 the LCID could always be used to uniquely identify one of the installed operating system-defined locales. The NLS APIs in Windows support these predefined LCIDs. Before Windows 8, the Windows team would add a few new supported locales for each new version, and each new locale they added would always have its own new unique LCID value to identify it. However, starting with Windows 8, Windows started adding new locales that do ***not*** have a unique pre-assigned LCID value to identify them. Such LCID-challenged locales are also referred to as Transient Locales. If you happen to use one of the old (now deprecated) Win32 APIs that use an LCID parameter or return value, and it encounters a Transient Locale, then you will get a Transient LCID from that API. Transient LCIDs are just there to satisfy the requirement that the API uses an LCID, but the actual Transient LCID value you will get at runtime is essentially meaningless. If you do anything with a Transient LCID, it will very likely cause data loss. There are only a handful of values reserved for use as Transient LCIDs, and there are far more Transient Locales than there are Transient LCIDs. The Transient LCIDs are handed out on a first-come-first-served basis when a user adds a Transient Locale to their Windows Language Profile. Because the Transient LCID could be re-assigned at any time (such as when the user changes their Language Profile), and because it can mean a different Locale for a different user and/or on a different system, that is why such LCIDs are called Transient.

| Reserved            Sort ID               Language ID         
|---------------------- --------------- -------------------------------
------------------------- ---------------- ------------------------------------- ---------
  31                   20   19          16   15                                0       bit
  ------------------------- ---------------- ------------------------------------- ---------

For example, LCID for English (US) (en-US) is 1033 which in binary is

```
00000000000000000000010000001001
+--------------+----+----------------+
     Reserved    Sort id  Language id      
```

