---
title: Running InfVerif from the command line
description: This topic lists the options that are available when you run InfVerif.exe from the command line.
ms.assetid: CC2DB624-FFEE-4049-ACE7-4A24B330BADB
ms.date: 04/20/2017
ms.localizationpriority: medium
---

# Running InfVerif from the command line


This topic lists the options that are available when you run InfVerif.exe from the command line.
> [!NOTE]
> InfVerif requires that each combined path and file name must be less than 260 characters.

```
USAGE: InfVerif.exe [/v] [/u | /universal] [/k] [/info] [/stampinf] [/l <path>]
                    [/osver TargetOSVersion>] [/product <ias file>] <files>

/v
        Display verbose file logging details.

/k
        Reports errors for Windows Update submission. (mode)

/u
        Reports errors if INF is not Universal. (mode)

/info
        Displays INF summary information.

/stampinf
        Treat $ARCH$ as a valid architecture, to validate
        pre-stampinf files.

/l <path>
        An inline-annotated HTML version of each INF
        file will be placed in the <path>.

/osver <TargetOsVersion>
        Process the INF for a specific target OS.
        Formatting is the same as a Models section, i.e. NTAMD64.6.0
        Matches the TargetOSVersion you would use in a Models section name (see link below)

/product <ias file>
        Validates all include/needs directives against
        the product definition in the ias file.

<files>
        A space-separated list of INF files to analyze.
        Wildcards (*) may be used.

Only one mode option may be passed at a time.
```

For examples of *TargetOSVersion* formatting, see Remarks section of [INF Manufacturer Section](../install/inf-manufacturer-section.md).

The verbose option adds a line to the output that specifies if the INF is valid or not.  Certain arguments are tagged as modes, where only one should be passed.

*New for Windows 10, version 1703:*  The info option is especially useful to verify INF applicability.  It reports each supported hardware ID along with valid architecture and minimum OS version.  You can use /info and /osver together to validate an INF's applicability across OS versions and architectures.

