---
title: Inf2Cat
description: Inf2Cat (Inf2Cat.exe) is a command-line tool that determines whether a driver package's INF file can be digitally-signed for a specified list of Windows versions.
ms.assetid: 5d85058e-4051-4321-a4c1-b1a71d232b7f
keywords:
- Inf2Cat Driver Development Tools
topic_type:
- apiref
api_name:
- Inf2Cat
api_type:
- NA
ms.date: 04/20/2017
ms.localizationpriority: medium
---

# Inf2Cat

Inf2Cat (Inf2Cat.exe) is a command-line tool that determines whether a [driver package's](../install/driver-packages.md) INF file can be digitally-signed for a specified list of Windows versions. If so, Inf2Cat generates the unsigned [catalog files](../install/catalog-files.md) that apply to the specified Windows versions.

```command
    Inf2Cat /driver:
    PackagePath
     /os:
    WindowsVersionList [/nocat] [/verbose] [/?] [other switches]
```

> [!TIP]
> If you see `DriverVer set to a date in the future` when building your driver, change your driver package project settings so that Inf2Cat sets `/uselocaltime`. To do so, use **Configuration Properties->Inf2Cat->General->Use Local Time**. Now both [Stampinf](stampinf-command-options.md) and Inf2Cat use local time.

The Inf2Cat tool is located in the Program Files\\Windows Kits\\8.0\\bin\\x86 or Program Files (x86)\\Windows Kits\\8.0\\bin\\x86 folder of the WDK.

## Switches and Arguments

**/driver:**<em>PackagePath</em>  
Specifies the path to the directory that contains the INF files for driver packages. If the specified directory contains INF files for multiple driver packages, Inf2Cat will create catalog files for each driver package.

> [!NOTE]
> You can use the **/drv:** switch in place of the **/driver:** switch.

**/nocat**  
Configures Inf2Cat to verify that the [driver package](../install/driver-packages.md) complies with the signing requirements for the specified Windows versions, but not to generate a catalog files.

**/os:**<em>WindowsVersionList</em>  
Configures Inf2Cat to verify that a [driver package's](../install/driver-packages.md) INF file complies with the signing requirements for the Windows versions that are specified by *WindowsVersionList*. *WindowsVersionList* is a comma-separated list that includes one or more of the following version identifiers.

|Windows version|Version identifier|
|--- |--- |
|Windows 10 x86 19H1 Edition|10_19H1_X86|
|Windows 10 x64 19H1 Edition|10_19H1_X64|
|Windows 10 ARM64 19H1 Edition|10_19H1_ARM64|
|Windows 10 x86 RS5 Edition|10_RS5_X86|
|Windows 10 x64 RS5 Edition|10_RS5_X64|
|Windows 10 ARM64 RS5 Edition|10_RS5_ARM64|
|Windows Server RS5 x64 Edition|ServerRS5_X64|
|Windows Server RS5 ARM64 Edition|ServerRS5_ARM64|
|Windows 10 x86 RS4 Edition|10_RS4_X86|
|Windows 10 x64 RS4 Edition|10_RS4_X64|
|Windows 10 ARM64 RS4 Edition|10_RS4_ARM64|
|Windows 10 x86 RS3 Edition|10_RS3_X86|
|Windows 10 x64 RS3 Edition|10_RS3_X64|
|Windows 10 ARM64 RS3 Edition|10_RS3_ARM64|
|Windows 10 x86 RS2 Edition|10_RS2_X86|
|Windows 10 x64 RS2 Edition|10_RS2_X64|
|Windows 10 x86 RS1 Edition|10_AU_X86|
|Windows 10 x64 RS1 Edition|10_AU_X64|
|Windows Server 2016 x64 Edition|SERVER2016_X64|
|Windows 10 x86 Edition|10_X86|
|Windows 10 x64 Edition|10_X64|
|Windows Server 2016|Server10_X64|
|Windows Server 2016 on ARM|Server10_ARM64|
|Windows 8.1 x86 Edition|6_3_X86|
|Windows 8.1 x64 Edition|6_3_X64|
|Windows 8.1 ARM Edition|6_3_ARM|
|Windows Server 2012 R2|Server6_3_X64|
|Windows 8 x64 Edition|8_X64|
|Windows 8 x86 Edition|8_X86|
|Windows 8 ARM Edition|8_ARM|
|Windows Server 2012|Server8_X64|
|Windows Server 2008 R2 x64 Edition|Server2008R2_X64|
|Windows Server 2008 R2 Itanium Edition|Server2008R2_IA64|
|Windows 7 x64 Edition|7_X64|
|Windows 7 x86 Edition|7_X86|
|Windows Server 2008 x64 Edition|Server2008_X64|
|Windows Server 2008 Itanium Edition|Server2008_IA64|
|Windows Server 2008 x86 Edition|Server2008_X86|
|Windows Vista x64 Edition|Vista_X64|
|Windows Vista x86 Edition|Vista_X86|
|Windows XP x64 Edition|XP_X64|
|Windows XP x86 Edition|XP_X86|
|Windows Server 2003 x64 Edition|Server2003_X64|
|Windows Server 2003 Itanium Edition|Server2003_IA64|
|Windows Server 2003 x86 Edition|Server2003_X86|

> [!NOTE]
> Starting with Windows Server 2008 R2, Windows server operating systems will no longer support x86-based platforms.

Inf2Cat ignores the case of the alphabetic characters of the version identifier strings. For example, vista\_x64 and Vista\_X64 are both valid identifiers for Windows Vista x64 Edition.

**/uselocaltime**  
Use local timezone while running driver timestamp verification tests. By default UTC is used.

**/nocat**  
Prevents the creation of the catalog(s).

**/verbose**  
Configures Inf2Cat to display detailed information in a command window.

**/?**  
Configures Inf2Cat to display help information in a command window.

**/drm**  
*Deprecated command line argument.*  
Add drm signature attribute in .inf file to add drm signature attribute.

**/pe**  
*Deprecated command line argument.*  
Add petrust signature attribute in .inf file to add petrust signature attribute.

**/pageHashes**  
Include page hashes with files.  Optionally followed by a list of files.

## Comments

The Inf2Cat tool replaced the Signability tool that was included in versions of the WDK prior to Windows Vista.

To use Inf2Cat, you must be a member of the Administrators group on the system.

The Inf2Cat tool checks [driver package's](../install/driver-packages.md) INF files for structural errors and verifies that a driver package can be digitally-signed. A driver package can be signed only if all of the files that are referenced in an INF file are present and the source files are in the correct location. If an INF file cannot be signed or if it contains structural errors, the driver package might not be installed correctly or might incorrectly display a driver signing warning dialog box during installation.

Inf2Cat generates a [catalog file](../install/catalog-files.md) only if the catalog file is specified in the driver package's INF file and the catalog file applies to one or more of the specified Windows versions. If the [**INF Version section**](../install/inf-version-section.md) of an INF file supplies only a **CatalogFile=**<em>filename.cat</em> directive, that catalog file applies to the entire driver package. To support [cross-platform installations](../install/creating-inf-files-for-multiple-platforms-and-operating-systems.md), the INF file should include **CatalogFile.**<em>PlatformExtension</em>**=**<em>unique-filename.cat</em> directives.

For more information about signing a driver package, see [Driver Signing](../install/driver-signing.md) and [Device and Driver Installation Fundamental Topics](https://docs.microsoft.com/windows-hardware/drivers/install/device-and-driver-installation-fundamental-topics).

## Examples

In the following example, c:\\MyDriver contains a [driver package](../install/driver-packages.md) whose INF file is MyInfFile.inf and the INF Version section in the INF file includes only the following **CatalogFile** directive:

```command
[Version]
. . .
CatalogFile=MyCatalogFile.cat
. . .
```

For this example, the following Inf2Cat command would verify whether the driver package can be signed for Windows 2000 and for the x86 versions of Windows Vista, Windows Server 2003, and Windows XP. If the package can be signed for these versions, Inf2Cat would create the unsigned catalog file MyCatalogFile.cat.

```command
Inf2Cat /driver:C:\MyDriver /os:2000,XP_X86,Server2003_X86,Vista_X86
```

In the following example, c:\\MyDriver contains a [driver package](../install/driver-packages.md) whose INF file is MyInfFile.inf and the INF **Version** section in the INF file includes only the following two **CatalogFile** directives with platform extensions:

```command
[Version]
. . .
CatalogFile.ntx86=MyCatalogFileX86.cat
CatalogFile.ntamd64=MyCatalogFileX64.cat
. . .
```

For this example, the following Inf2Cat command would verify whether the driver package can be signed for Windows 2000 and the x86 versions of Windows Vista, Windows Server 2003, and Windows XP. In addition, the command would verify whether the driver package can be signed for the x64 editions of Windows Vista, Windows Server 2003, and Windows XP. If the package can be signed for all of these versions, Inf2Cat will create the unsigned catalog files MyCatalogFileX86.cat and MyCatalogFileX64.cat.

```command
Inf2Cat /driver:C:\MyDriver /os:2000,XP_X86,XP_X64,Server2003_X86,Server2003_X64,Vista_X86,Vista_X64
```

For more information about how to use Inf2Cat to create a catalog file, see [Creating a Catalog File for a PnP Driver Package](../install/creating-a-catalog-file-for-a-pnp-driver-package.md).