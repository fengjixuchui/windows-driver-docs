---
title: DEVPKEY_DeviceClass_ClassName
description: DEVPKEY_DeviceClass_ClassName
ms.assetid: dc085e27-06c7-49ca-808f-3d1952cb8aa9
keywords: ["DEVPKEY_DeviceClass_ClassName Device and Driver Installation"]
topic_type:
- apiref
api_name:
- DEVPKEY_DeviceClass_ClassName
api_location:
- Devpkey.h
api_type:
- HeaderDef
ms.localizationpriority: medium
ms.date: 10/17/2018
---

# DEVPKEY_DeviceClass_ClassName


The DEVPKEY_DeviceClass_ClassName device property represents the class name of a [device setup class](https://docs.microsoft.com/windows-hardware/drivers/install/device-setup-classes).

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
<td align="left"><p>DEVPKEY_DeviceClass_ClassName</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Property-data-type identifier</strong></p></td>
<td align="left"><p><a href="devprop-type-string.md" data-raw-source="[&lt;strong&gt;DEVPROP_TYPE_STRING&lt;/strong&gt;](devprop-type-string.md)"><strong>DEVPROP_TYPE_STRING</strong></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Property access</strong></p></td>
<td align="left"><p>Read-only access by installation applications and installers</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Localized?</strong></p></td>
<td align="left"><p>No</p></td>
</tr>
</tbody>
</table>

 

Remarks
-------

The value of DEVPKEY_DeviceClass_ClassName is set by the **Class** directive that is included in the [**INF Version section**](https://docs.microsoft.com/windows-hardware/drivers/install/inf-driverver-directive) that installs the device setup class.

You can call [**SetupDiGetClassProperty**](https://docs.microsoft.com/windows/desktop/api/setupapi/nf-setupapi-setupdigetclasspropertyw) or [**SetupDiGetClassPropertyEx**](https://docs.microsoft.com/windows/desktop/api/setupapi/nf-setupapi-setupdigetclasspropertyexw) to retrieve the value of DEVPKEY_DeviceClass_ClassName.

Windows Server 2003, Windows XP, and Windows 2000 support this property, but do not support the DEVPKEY_DeviceClass_ClassName property key. For information about how to access the name of a device setup class on Windows Server 2003, Windows XP, and Windows 2000, see [Accessing the Friendly Name and Class Name of a Device Setup Class](https://docs.microsoft.com/windows-hardware/drivers/install/accessing-the-friendly-name-and-class-name-of-a-device-setup-class).

Requirements
------------

**Version**: Windows Vista and later versions of Windows
**Header**: Devpkey.h (include Devpkey.h)


## See also


[**INF Version section**](https://docs.microsoft.com/windows-hardware/drivers/install/inf-driverver-directive)

[**SetupDiGetClassProperty**](https://docs.microsoft.com/windows/desktop/api/setupapi/nf-setupapi-setupdigetclasspropertyw)

[**SetupDiGetClassPropertyEx**](https://docs.microsoft.com/windows/desktop/api/setupapi/nf-setupapi-setupdigetclasspropertyexw)

[**SetupDiClassNameFromGuid**](https://docs.microsoft.com/windows/desktop/api/setupapi/nf-setupapi-setupdiclassnamefromguida)

 

 






