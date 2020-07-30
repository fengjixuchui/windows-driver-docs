---
title: DEVPKEY_DeviceClass_SecuritySDS
description: DEVPKEY_DeviceClass_SecuritySDS
ms.assetid: 463e8af1-a1cc-4c05-94c9-f1fbaf5928f9
keywords: ["DEVPKEY_DeviceClass_SecuritySDS Device and Driver Installation"]
topic_type:
- apiref
api_name:
- DEVPKEY_DeviceClass_SecuritySDS
api_location:
- Devpkey.h
api_type:
- HeaderDef
ms.localizationpriority: medium
ms.date: 10/17/2018
---

# DEVPKEY_DeviceClass_SecuritySDS


The DEVPKEY_DeviceClass_SecuritySDS device property represents a security descriptor string for a [device setup class](https://docs.microsoft.com/windows-hardware/drivers/install/device-setup-classes).

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
<td align="left"><p>DEVPKEY_DeviceClass_SecuritySDS</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Property-data-type identifier</strong></p></td>
<td align="left"><p><a href="devprop-type-security-descriptor-string.md" data-raw-source="[&lt;strong&gt;DEVPROP_TYPE_SECURITY_DESCRIPTOR_STRING&lt;/strong&gt;](devprop-type-security-descriptor-string.md)"><strong>DEVPROP_TYPE_SECURITY_DESCRIPTOR_STRING</strong></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Property access</strong></p></td>
<td align="left"><p>Read and write access by installation applications and installers</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Corresponding SPCRP_</strong><em>Xxx</em> <strong>identifier</strong></p></td>
<td align="left"><p>SPCRP_SECURITY_SDS</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Localized?</strong></p></td>
<td align="left"><p>No</p></td>
</tr>
</tbody>
</table>

 

Remarks
-------

You can set the value of DEVPKEY_DeviceClass_SecuritySDS either during or after an installation application installs a device setup class. For more information about how to set this property, see [Creating Secure Device Installations](https://docs.microsoft.com/windows-hardware/drivers/install/creating-secure-device-installations).

You can retrieve the value of DEVPKEY_DeviceClass_SecuritySDS by calling [**SetupDiGetClassProperty**](https://docs.microsoft.com/windows/desktop/api/setupapi/nf-setupapi-setupdigetclasspropertyw) or [**SetupDiGetClassPropertyEx**](https://docs.microsoft.com/windows/desktop/api/setupapi/nf-setupapi-setupdigetclasspropertyexw). You can set DEVPKEY_DeviceClass_SecuritySDS by calling [**SetupDiSetClassProperty**](https://docs.microsoft.com/windows/desktop/api/setupapi/nf-setupapi-setupdisetclasspropertyw) or [**SetupDiSetClassPropertyEx**](https://docs.microsoft.com/windows/desktop/api/setupapi/nf-setupapi-setupdisetclasspropertyexw).

Windows Server 2003 and Windows XP support this property, but do not support the DEVPKEY_DeviceClass_SecuritySDS property key. On these earlier versions of Windows, you can use the SPCRP_SECURITY_SDS identifier to access the value of this property. For information about how to access the value of this property, see [Retrieving Device Setup Class SPCRP_Xxx Properties](https://docs.microsoft.com/windows-hardware/drivers/install/retrieving-spcrp-xxx-properties) and [Setting Device Setup Class SPCRP_Xxx Properties](https://docs.microsoft.com/windows-hardware/drivers/install/setting-spcrp-xxx-properties).

Requirements
------------

**Version**: Windows Vista and later versions of Windows
**Header**: Devpkey.h (include Devpkey.h)


## See also


[**SetupDiGetClassProperty**](https://docs.microsoft.com/windows/desktop/api/setupapi/nf-setupapi-setupdigetclasspropertyw)

[**SetupDiGetClassPropertyEx**](https://docs.microsoft.com/windows/desktop/api/setupapi/nf-setupapi-setupdigetclasspropertyexw)

[**SetupDiSetClassProperty**](https://docs.microsoft.com/windows/desktop/api/setupapi/nf-setupapi-setupdisetclasspropertyw)

[**SetupDiSetClassPropertyEx**](https://docs.microsoft.com/windows/desktop/api/setupapi/nf-setupapi-setupdisetclasspropertyexw)

 

 






