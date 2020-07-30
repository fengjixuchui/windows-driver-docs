---
title: DEVPKEY_DeviceInterface_Enabled
description: DEVPKEY_DeviceInterface_Enabled
ms.assetid: 8e7ea36c-827d-43bd-b424-41c06ba8c20d
keywords: ["DEVPKEY_DeviceInterface_Enabled Device and Driver Installation"]
topic_type:
- apiref
api_name:
- DEVPKEY_DeviceInterface_Enabled
api_location:
- Devpkey.h
api_type:
- HeaderDef
ms.localizationpriority: medium
ms.date: 10/17/2018
---

# DEVPKEY_DeviceInterface_Enabled


The **DeviceInterfaceEnabled** device property represents a Boolean flag that indicates whether a device interface is enabled.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr>
<th>Attribute</th>
<th>Value</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>Property key</strong></p></td>
<td align="left"><p>DEVPKEY_DeviceInterface_Enabled</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Property-data-type identifier</strong></p></td>
<td align="left"><p><a href="devprop-type-boolean.md" data-raw-source="[&lt;strong&gt;DEVPROP_TYPE_BOOLEAN&lt;/strong&gt;](devprop-type-boolean.md)"><strong>DEVPROP_TYPE_BOOLEAN</strong></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Property access</strong></p></td>
<td align="left"><p>Read-only by installation applications and installers</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Localized?</strong></p></td>
<td align="left"><p>No</p></td>
</tr>
</tbody>
</table>

 

Remarks
-------

If the value of DEVPKEY_DeviceInterface_Enabled is DEVPROP_TRUE, the interface is enabled. Otherwise, the interface is not enabled.

You can call [**SetupDiGetDeviceInterfaceProperty**](https://docs.microsoft.com/windows/desktop/api/setupapi/nf-setupapi-setupdigetdeviceinterfacepropertyw) to retrieve the value of DEVPKEY_DeviceInterface_Enabled.

Windows Server 2003, Windows XP, and Windows 2000 support this property, but do not support the DEVPKEY_DeviceInterface_Enabled property key. For information about how to retrieve the activity status of a device interface on these earlier versions of Windows, see the information about how to use [**SetupDiEnumDeviceInterfaces**](https://docs.microsoft.com/windows/desktop/api/setupapi/nf-setupapi-setupdienumdeviceinterfaces) that is provided in [Accessing Device Interface Properties](https://docs.microsoft.com/windows-hardware/drivers/install/accessing-device-interface-properties).

For more information about device interfaces, see [Device Interface Classes](https://docs.microsoft.com/windows-hardware/drivers/install/device-interface-classes) and the [**INF AddInterface Directive**](https://docs.microsoft.com/windows-hardware/drivers/install/inf-addinterface-directive).

Requirements
------------

**Version**: Windows Vista and later versions of Windows
**Header**: Devpkey.h (include Devpkey.h)


## See also


[**INF AddInterface Directive**](https://docs.microsoft.com/windows-hardware/drivers/install/inf-addinterface-directive)

[**SetupDiEnumDeviceInterfaces**](https://docs.microsoft.com/windows/desktop/api/setupapi/nf-setupapi-setupdienumdeviceinterfaces)

[**SetupDiGetDeviceInterfaceProperty**](https://docs.microsoft.com/windows/desktop/api/setupapi/nf-setupapi-setupdigetdeviceinterfacepropertyw)

 

 






