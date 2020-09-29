---
title: Supporting Device Fonts
description: Supporting Device Fonts
ms.assetid: 9ca3269d-3f87-4d8a-a897-7305ac172227
keywords:
- printer graphics DLL WDK , device fonts
- graphics DLL WDK printer , device fonts
- device fonts WDK printer graphics
- fonts WDK printer graphics
ms.date: 04/20/2017
ms.localizationpriority: medium
---

# Supporting Device Fonts





If a printer provides device fonts, the printer graphics DLL must define a [**DrvTextOut**](/windows/win32/api/winddi/nf-winddi-drvtextout) function to generate text output commands. The graphics DLL must also define the following functions:

[**DrvQueryAdvanceWidths**](/windows/win32/api/winddi/nf-winddi-drvqueryadvancewidths)
[**DrvQueryFont**](/windows/win32/api/winddi/nf-winddi-drvqueryfont)
[**DrvQueryFontData**](/windows/win32/api/winddi/nf-winddi-drvqueryfontdata)
[**DrvQueryFontTree**](/windows/win32/api/winddi/nf-winddi-drvqueryfonttree)
For more information about supporting device fonts, see [Supporting Graphics DDI Font and Text Functions](../display/supporting-graphics-ddi-font-and-text-functions.md).

 

