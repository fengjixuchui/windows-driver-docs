---
title: Retrieving Information from an INF File
description: Retrieving Information from an INF File
ms.assetid: 4174357f-bca3-43b8-8ad6-331b9accd905
keywords:
- INF files WDK device installations , retrieving information
- retrieving INF file information
- status information WDK INF files
ms.date: 04/20/2017
ms.localizationpriority: medium
---

# Retrieving Information from an INF File





Once you have a handle to an INF file, you can retrieve information from it in a variety of ways. Functions such as [**SetupGetInfInformation**](https://docs.microsoft.com/windows/desktop/api/setupapi/nf-setupapi-setupgetinfinformationa), [**SetupQueryInfFileInformation**](https://docs.microsoft.com/windows/desktop/api/setupapi/nf-setupapi-setupqueryinffileinformationa), and [**SetupQueryInfVersionInformation**](https://docs.microsoft.com/windows/desktop/api/setupapi/nf-setupapi-setupqueryinfversioninformationa) retrieve information about the specified INF file.

Other functions, such as [**SetupGetSourceInfo**](https://docs.microsoft.com/windows/desktop/api/setupapi/nf-setupapi-setupgetsourceinfoa) and [**SetupGetTargetPath**](https://docs.microsoft.com/windows/desktop/api/setupapi/nf-setupapi-setupgettargetpatha), obtain information about the source files and target directories.

Functions such as [**SetupGetLineText**](https://docs.microsoft.com/windows/desktop/api/setupapi/nf-setupapi-setupgetlinetexta) and [**SetupGetStringField**](https://docs.microsoft.com/windows/desktop/api/setupapi/nf-setupapi-setupgetstringfielda) enable you to directly access information that is stored in a line or field of an INF file. These functions are used internally by the higher-level [SetupAPI](setupapi.md) functions but are available if you have to directly access information at the line or field level.

 

 





