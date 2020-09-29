---
title: INF Files for PSHED Plug-Ins
description: INF Files for PSHED Plug-Ins
ms.assetid: 60bb9902-c558-4ee1-9b33-1a08885e7c06
keywords:
- PSHED plug-ins WDK WHEA , INF files
- platform-specific hardware error driver plug-ins WDK WHEA , INF files
- INF files WDK WHEA
ms.date: 04/20/2017
ms.localizationpriority: medium
---

# INF Files for PSHED Plug-Ins


A PSHED plug-in is installed by an [information (INF) file](https://docs.microsoft.com/windows-hardware/drivers/install/inf-files). INF files for PSHED plug-ins contain the following standard INF file sections:

[**INF Version Section**](../install/inf-version-section.md)

[**INF SourceDisksNames Section**](../install/inf-sourcedisksnames-section.md)

[**INF SourceDisksFiles Section**](../install/inf-sourcedisksfiles-section.md)

[**INF DestinationDirs Section**](../install/inf-destinationdirs-section.md)

[**INF Manufacturer Section**](../install/inf-manufacturer-section.md)

[**INF *Models* Section**](../install/inf-models-section.md)

[**INF *DDInstall* Section**](../install/inf-ddinstall-section.md)

[**INF *DDInstall*.Services Section**](../install/inf-ddinstall-services-section.md)

[**INF Strings Section**](../install/inf-strings-section.md)

Within the [**INF *Models* section**](../install/inf-models-section.md), the platform vendor can use any [hardware identifier (ID)](../install/hardware-ids.md) for the PSHED plug-in. The hardware ID is specified by using the *hw-id* entry in the *Models* section, and can be a hardware ID in the ACPI namespace or another device namespace. The vendor can also specify a [compatible ID](../install/compatible-ids.md) with a value of *PNP0C33*. This compatible ID is used to define to a Microsoft-compatible hardware error device. The vendor specifies the compatible ID by using the *compatible-id* entry in the *Models* section.

A PSHED plug-in's INF file must also include an [**AddReg**](../install/inf-addreg-directive.md) directive that references a section in the file that adds an entry to the **System**\\**CurrentControlSet**\\**Control**\\**PSHED**\\**Plugins** key in the registry. This entry informs the PSHED that the PSHED plug-in is installed in the system. This allows the PSHED to verify that all the installed PSHED plug-ins are successfully loaded every time that the system is started.

For example:

```cpp
;
; Example PSHED plug-in INF file
;

[Version]
Signature = "$Windows NT$"
Provider = %Msft%
CatalogFile = "ExamplePSHEDPlugin.cat"
DriverVer = 01/01/06,1.0

[SourceDiskNames]
1 = %DiskName%

[SourceDiskFiles]
%FileName% = 1

[DestinationDirs]
DefaultDestDir = 12 ; %SystemRoot%\system32\drivers
ExamplePSHEDPlugin.DriverFiles = 12 ; %SystemRoot%\system32\drivers

[Manufacturer]
%Msft% = Microsoft

[Microsoft]
%DeviceDesc% = ExamplePSHEDPluginInstall,%DeviceId%

[ExamplePSHEDPluginInstall]
OptionDesc = %Description%
CopyFiles = ExamplePSHEDPlugin.DriverFiles
AddReg = ExamaplePSHEDPlugin.AddReg

[ExamplePSHEDPluginInstall.Services]
AddService = %ServiceName%,,ExamplePSHEDPlugin.Service

[ExamplePSHEDPlugin.DriverFiles]
%FileName%,,,0x00000040 ; COPYFLG_OVERWRITE_OLDER_ONLY

[ExamplePSHEDPlugin.AddReg]
HKLM,%PSHEDControlPath%,%ServiceName%,0x00000000,%FileName%

[ExamplePSHEDPlugin.Service]
DisplayName = %ServiceName%
Description = %ServiceDesc%
ServiceType = 1  ; SERVICE_KERNEL_DRIVER
StartType = 3    ; SERVICE_DEMAND_START
ErrorControl = 1 ; SERVICE_ERROR_NORMAL
ServiceBinary = %12%\%FileName%

[Strings]
%Msft% = "Microsoft Corporation"
%DiskName% = "Example PSHED Plug-In Installation Disk"
%FileName% = "ExamplePSHEDPlugin.sys"
%DeviceDesc% = "Example PSHED Plug-In Device"
%DeviceId% = "ACPI\PSHEDPI"
%Description% = "Example PSHED Plug-In"
%ServiceName% = "ExamplePSHEDPlugin"
%ServiceDesc% = "Example PSHED Plug-In"
%PSHEDControlPath% = "System\CurrentControlSet\Control\PSHED\Plugins"
```

 

