---
title: EFI_USBFN_PORT_TYPE
description: EFI_USBFN_PORT_TYPE
ms.assetid: 2596dd4f-26bd-454b-9550-a89c7e1f790b
ms.date: 05/21/2020
ms.localizationpriority: medium
---

# EFI\_USBFN\_PORT\_TYPE

This enumeration specifies the USB port type.

## Syntax

```cpp
typedef enum _EFI_USBFN_PORT_TYPE
{
    EfiUsbUnknownPort = 0,
    EfiUsbStandardDownstreamPort,
    EfiUsbChargingDownstreamPort,
    EfiUsbDedicatedChargingPort,
    EfiUsbInvalidDedicatedChargingPort
} EFI_USBFN_PORT_TYPE;
```

## Constants

| Value | Description |
| --- | --- |
| EfiUsbUnknownPort | Unknown Port - Driver internal default port type; this is never returned by the driver with a success status code. |
| EfiUsbStandardDownstreamPort | Standard Downstream Port - Standard USB host. |
| EfiUsbChargingDownstreamPort | Charging Downstream Port - Standard USB host. |
| EfiUsbDedicatedChargingPort | Dedicated Charging Port – A wall-charger, not USB host. |
| EfiUsbInvalidDedicatedChargingPort | Invalid Dedicated Charging Port – Not a USB host or dedicated charging port. |

## Remarks

For more information, refer to "Battery Charging Specification, Revision 1.1” on the [USB.org](https://www.usb.org/documents) website.

## Requirements

**Header:** User generated
