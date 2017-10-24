---
title: Watch Your String Buffer Sizes
description: 
ms.assetid: c09cea43-364a-44db-9b7c-9ea0cea77b68
ms.date: 10/20/2016
---

# Watch Your String Buffer Sizes

Length restrictions for strings are potential bugs that can cause major problems. For example, a product build was broken because of the German translation for the following string:

"Press Ctrl+Alt+Del to restart."

When translated into German, this string almost doubled in size to:

"Drücken Sie Strg+Alt+Entf, um den Computer neu zu starten."

The increased string size caused the buffer to overflow, which in turn crashed the system. The message was supposed to go into a boot sector of a certain byte size, and there was no space for a longer message. The only thing that can be done for this type of problem is to make sure that you communicate to localizers how much room they have for their translation.

Along these same lines, buffer overruns, when there is no physical restriction, are notorious for bugs even in nonlocalized software. Localizing strings tends to reveal buffer overrun problems. These types of problems can be eliminated if buffers are dynamic or are allowed to have the maximum buffer size. Estimating size requirements will be discussed in the next section, which will explain how an optimal UI design makes localization easier.


