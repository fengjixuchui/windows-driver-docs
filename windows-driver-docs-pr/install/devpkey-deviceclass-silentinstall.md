---
title: DEVPKEY_DeviceClass_SilentInstall
description: DEVPKEY_DeviceClass_SilentInstall
ms.assetid: db9ff5d2-020f-47bc-a1e3-2b305b5270e9
keywords: ["DEVPKEY_DeviceClass_SilentInstall Device and Driver Installation"]
topic_type:
- apiref
api_name:
- DEVPKEY_DeviceClass_SilentInstall
api_location:
- Devpkey.h
api_type:
- HeaderDef
ms.localizationpriority: medium
ms.date: 10/17/2018
---

# DEVPKEY_DeviceClass_SilentInstall


The DEVPKEY_DeviceClass_SilentInstall device property represents a Boolean flag that controls whether devices in a [device setup class](https://docs.microsoft.com/windows-hardware/drivers/install/device-setup-classes) should be installed, if possible, without displaying any user interface items.

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
<td align="left"><p>DEVPKEY_DeviceClass_SilentInstall</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Property-data-type identifier</strong></p></td>
<td align="left"><p><a href="devprop-type-boolean.md" data-raw-source="[&lt;strong&gt;DEVPROP_TYPE_BOOLEAN&lt;/strong&gt;](devprop-type-boolean.md)"><strong>DEVPROP_TYPE_BOOLEAN</strong></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Property access</strong></p></td>
<td align="left"><p>Read-only access by installation applications and installers</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Corresponding registry value name</strong></p></td>
<td align="left"><p><strong>SilentInstall</strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Localized?</strong></p></td>
<td align="left"><p>No</p></td>
</tr>
</tbody>
</table>

 

Remarks
-------

If the value of DEVPKEY_DeviceClass_SilentInstall is set to DEVPROP_TRUE, Windows installs a driver for a device without displaying any user interface items if the driver is already preinstalled in the driver store. Otherwise, Windows does not suppress the display of user interface items.

The **SilentInstall** registry value for a device setup class can be set by an [**INF AddReg directive**](https://docs.microsoft.com/windows-hardware/drivers/install/inf-addreg-directive) that is included in the [**INF ClassInstall32 section**](https://docs.microsoft.com/windows-hardware/drivers/install/inf-classinstall32-section) of the INF file that installs the class.

You can call [**SetupDiGetClassProperty**](https://docs.microsoft.com/windows/desktop/api/setupapi/nf-setupapi-setupdigetclasspropertyw) or [**SetupDiGetClassPropertyEx**](https://docs.microsoft.com/windows/desktop/api/setupapi/nf-setupapi-setupdigetclasspropertyexw) to retrieve the value of DEVPKEY_DeviceClass_SilentInstall.

Windows Server 2003, Windows XP, and Windows 2000 support this property, but do not support the DEVPKEY_DeviceClass_SilentInstall property key. You can access the value of this property by accessing the corresponding **SilentInstall** registry value under the class registry key. For information about how to access value entries under the class registry key, see [Accessing Registry Entry Values Under the Class Registry Key](https://docs.microsoft.com/windows-hardware/drivers/install/accessing-registry-entry-values-under-the-class-registry-key).

Requirements
------------

**Version**: Windows Vista and later versions of Windows
**Header**: Devpkey.h (include Devpkey.h)


## See also


[**INF AddReg Directive**](https://docs.microsoft.com/windows-hardware/drivers/install/inf-addreg-directive)

[**INF ClassInstall32 Section**](https://docs.microsoft.com/windows-hardware/drivers/install/inf-classinstall32-section)

[**SetupDiGetClassProperty**](https://docs.microsoft.com/windows/desktop/api/setupapi/nf-setupapi-setupdigetclasspropertyw)

[**SetupDiGetClassPropertyEx**](https://docs.microsoft.com/windows/desktop/api/setupapi/nf-setupapi-setupdigetclasspropertyexw)

 

 






