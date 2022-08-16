---
title: Printing and paper size
description: If your application needs to print, you should allow the default paper size to be configurable for globalization purpose.
ms.assetid: fe36768d-ffc5-4271-b308-9aa47154c722
ms.date: 11/14/2016
---
# Printing

Printing is a major concern that should be addressed at the early stages of your project.
Printing is a globalization-sensitive issue due to the factors in this topic.

## Paper size

Paper sizes conventionally used in any given region do not satisfy the needs of all users in the world market.
Most countries/regions in Europe and Asia use an international standard known as the A-series.
A4, for example (297 x 210 mm) is slightly longer and narrower than the 8 1/2 x 11 inch letter size (279 x 216 mm) commonly used in the US and Canada.
There are standardized B, C, and D series, and many specialized sizes, including those based on historical printing and publishing sizes.
Thus, if your application needs to print, you should allow the default paper size to be configurable.

Win32 NLS APIs can help you select an appropriate default paper size associated with a given locale.
This information can be obtained from the [GetLocaleInfoEx](/windows/desktop/api/winnls/nf-winnls-getlocaleinfoex) API with the LCType flag set to LOCALE\_IPAPERSIZE.
The returned value is one of the following.

| Country/Region code | Format |
| --- | --- |
| 1 | U.S. Letter |
| 5 | U.S. Legal |
| 8 | A3 |
| 9 | A4 |

See also [ISO 216](https://www.iso.org/standard/36631.html).

## Character sets

Issues with printer drivers and printer technologies are more likely as support for more languages is added to Windows.
Ensure that the work you did to support fonts, complex scripts, and bidirectional text extends to printing.

## Printing areas

When considering printing, you should ensure the following areas are covered.

- **Regular document printing**:
  Ensure any special characters, vowels, diacritics, kashidas, and headers and footers are covered.
  For bidirectional languages, you may need to set your document direction to right-to-left.

- **Print preview**:
  Most printing issues show up in Print Preview as well.
  Some of the common issues occur with character clipping, disconnected characters, zooming in/out, blank print preview content, and headers and footers.

- **Headers and footers**:
  As with the regular document surface, this area should be globalized.

- **Other formats, such as XPS and PDF printing**:
  If your application supports printing to files in XPS, PDF or other formats, then all the above issues should be applied to these document types.
