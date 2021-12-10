---
title: Paper size
description: If your application needs to print, you should allow the default paper size to be configurable for globalization purpose.
ms.assetid: fe36768d-ffc5-4271-b308-9aa47154c722
ms.date: 11/14/2016
---
# Printing

Printing is a major concern that should be addressed at the early stages of your project.
Printing is a World Ready - sensitive issue due to the factors in this topic.

## Paper Size

Paper sizes in the United States and Canada (such as letter, legal, and so on) do not satisfy the needs of all users in the world market.
For example, most countries in Europe and Asia use a slightly larger standard known as “A4” (297 x 210 mm) that is slightly longer and narrower than the U.S. letter size (279 x 216 mm).
Thus, if your application needs to print, you should allow the default paper size to be configurable.
Win32 NLS APIs can help you detect the default paper size associated with a given locale.
This information can be obtained from the [GetLocaleInfoEx](/windows/desktop/api/winnls/nf-winnls-getlocaleinfoex) *API with the LCType* flag set to LOCALE\_IPAPERSIZE.
The returned value is one of the following.

| Country | Format |
| --- | --- |
| 1 | U.S. Letter |
| 5 | U.S. Legal |
| 8 | A3 |
| 9 | A4 |

See also [ISO 216 Standard Paper Size](http://en.wikipedia.org/wiki/ISO_216) for reference.

## Character sets

Issues with by printer drivers and printer technologies are more likely as support for more languages is added.
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
  As with the regular document surface, this area should be World Ready.

- **Other formats, such as XPS and PDF printing**:
  If your application supports printing XPS or PDF documents, then all the above issues should be applied to these document types.
