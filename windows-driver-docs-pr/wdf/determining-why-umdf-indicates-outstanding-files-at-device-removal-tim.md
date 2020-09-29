---
title: UMDF Indicates Outstanding Files at Device Removal Time
description: Describes how to use Wudfext.dll to determine why UMDF indicates that there are outstanding files when you remove a device.
ms.assetid: 9a8b3b69-1192-40c1-895b-4abfc01c1ca7
keywords:
- debugging scenarios WDK UMDF , UMDF indicates outstanding files at device removal time
- UMDF WDK , debugging scenarios, UMDF indicates outstanding files at device removal time
- UMDF WDK , UMDF indicates outstanding files at device removal time
ms.date: 04/20/2017
ms.localizationpriority: medium
---

# Determining Why UMDF Indicates Outstanding Files at Device Removal Time


This topic describes how you can use the Wudfext.dll debugger extensions in conjunction with a User-Mode Driver Framework (UMDF) version 1 or 2 driver to determine why UMDF indicates that there are outstanding files when you remove a device.

For UMDF version 1, you'll use extension commands implemented in wudfext.dll. Starting in UMDF version 2, you'll use extension commands implemented in wdfkd.dll.

To determine why UMDF indicates outstanding files, use the following steps:

1.  Use [**!wudfext.umdevstack**](../debugger/-wudfext-umdevstack.md) (UMDF 1) or [**!wdfkd.wdfumdevstack**](../debugger/-wdfkd-wdfumdevstack.md) (UMDF 2) to dump the device stack. The dump includes outstanding UMDF intra-stack files (that is, file objects that a driver in the stack created as opposed to file objects that were created by an application or by a driver in another stack).

2.  For each intra-stack file, run [**!wudfext.umfile**](../debugger/-wudfext-umfile.md) (UMDF 1) or [**!wdfkd.wdfumfile**](../debugger/-wdfkd-wdfumfile.md) (UMDF 2) to obtain information about the file.

    The output includes the list of IRPs that are pending.

3.  Determine why each IRP is outstanding by using [**!wudfext.umirp**](../debugger/-wudfext-umirp.md) (UMDF 1) or [**!wdfkd.wdfumirp**](../debugger/-wdfkd-wdfumirp.md) (UMDF 2) to obtain information about the IRP.

    From the output of each [**!wudfext.umirp**](../debugger/-wudfext-umirp.md) or [**!wdfkd.wdfumirp**](../debugger/-wdfkd-wdfumirp.md):

    -   Determine if the IRP completed.
    -   Determine if a driver-created request was not deleted either explicitly by the driver or implicitly by the object tree.

 

