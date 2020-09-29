---
title: Deleting the Registry Keys of a Device
description: Deleting the Registry Keys of a Device
ms.assetid: BA7AB3B4-9751-4e53-98AD-2B920F7223A1
keywords:
- registry WDK device installations , deleting a device's registry keys
- deleting registry keys WDK device installations
ms.date: 04/20/2017
ms.localizationpriority: medium
---

# Deleting the Registry Keys of a Device


You should not use **SetupDiDeleteDevRegKey** or *hardware keys* for the device for the following reasons:

-   [**SetupDiDeleteDevRegKey**](/windows/win32/api/setupapi/nf-setupapi-setupdideletedevregkey) removes all custom settings in registry keys. This includes the following:

    -   Settings that were specified during installation.

    -   Settings that were created or modified by the device driver.

    -   Settings that were created or modified by applications or other components.

    [**SetupDiDeleteDevRegKey**](/windows/win32/api/setupapi/nf-setupapi-setupdideletedevregkey) also removes critical device installation state.

-   Software or hardware keys that are opened by using [**SetupDiOpenDevRegKey**](/windows/win32/api/setupapi/nf-setupapi-setupdiopendevregkey) with a scope of DICS_FLAG_GLOBAL contain data about the device installation state. Software or hardware keys that are accessed with a scope of DICS_FLAG_CONFIGSPECIFIC do not contain device installation state.

    In either case, deleting these software or hardware keys could have implications for other device installation components.

You should not make assumptions about whether device registry keys are present. When the device is uninstalled, the system automatically deletes all software and hardware keys for the device.

You can safely create and delete registry subkeys under the hardware or software keys by using standard registry functions. By using these functions, you avoid naming collisions between the system and other components. Also, if you create subkeys by using these functions, the subkey inherits the default permissions of the parent registry key. For more information, see [Opening, Creating, and Closing Keys](https://go.microsoft.com/fwlink/p/?linkid=194541).

For more information about the standard registry functions, see [Registry Functions](https://go.microsoft.com/fwlink/p/?linkid=194529).

 

