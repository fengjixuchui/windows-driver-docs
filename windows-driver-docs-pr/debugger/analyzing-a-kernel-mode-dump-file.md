---
title: Analyzing a Kernel-Mode Dump File
description: Analyzing a Kernel-Mode Dump File
ms.assetid: 2bda51c2-b022-4740-8df9-5a2cf2382e3e
keywords: ["dump file, analyzing a kernel-mode dump file"]
ms.date: 06/05/2020
ms.localizationpriority: medium
---

# Analyzing a Kernel-Mode Dump File

This section includes:

[Analyzing a Kernel-Mode Dump File with KD](analyzing-a-kernel-mode-dump-file-with-kd.md)

[Analyzing a Kernel-Mode Dump File with WinDbg](analyzing-a-kernel-mode-dump-file-with-windbg.md)

### Installing Symbol Files

Regardless of which tool you use, you need to install the symbol files for the version of Windows that generated the dump file. These files will be used by the debugger you choose to use to analyze the dump file. For more information about the proper installation of symbol files, see [Installing Windows Symbol Files](installing-windows-symbol-files.md).

### DumpExam

The DumpExam tool is obsolete. It is no longer needed in the analysis of a crash dump file.
