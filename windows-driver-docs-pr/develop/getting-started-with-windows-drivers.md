---
ms.assetid: E109BD80-F9CB-4F1F-A6FD-1142E27EC6AD
title: Getting Started with Windows Drivers
description: Windows Drivers allow you to create one driver that will run on on both Windows 10X and Windows Desktop.
ms.date: 04/28/2020
ms.localizationpriority: medium
---

# Getting Started with Windows Drivers

Starting at some point after Windows 10, version 2004, drivers that run on Windows will be classified as either *Windows Drivers* or *Windows Desktop Drivers*. 

Windows Drivers will run on all Window 10 variants, including Windows 10X and Windows 10 Desktop editions.  Windows Desktop Drivers will *only* run on Windows 10 Desktop editions.  

The *Windows Driver* classification will extend and replace the current *Universal Driver* classification. 

This page provides a preview of the upcoming requirements for Windows Drivers.  

> [!NOTE]
> The distinction between Windows Drivers and Windows Desktop Drivers does not affect any driver being submitted and certified for Windows 10 Version 2004.  Changes in certification and submission will happen at a later date.


## Windows Drivers Requirements

When Windows Drivers become a certification option, the following requirements will apply:

- Compliant with [DCH Design Principles](dch-principles-best-practices.md).
- Follow the principles of [Driver Package Isolation](driver-isolation.md).
- Follow [API Layering Requirements](api-layering.md).
- Certified with [Windows Hardware Compatibility Program Certification Process](/windows-hardware/design/compatibility/whcp-certification-process) using the [Hardware Lab Kit](/windows-hardware/test/hlk/). Note that the Windows Hardware Compatibility Program Certification Process requirements apply to both KMDF and UMDF drivers.

## Windows Drivers vs. Windows Desktop Drivers

The following table summarizes the distinctions above:

|     Feature                                                         |Windows Drivers|Windows Desktop Drivers |
| --------------------------------------------------------------------|:-------------:|:----------------------:|
| Run on Windows 10 Desktop                                           | Yes           | Yes                    |
| Run on Windows 10X                                                  | Yes           | No                     |
| Must be certified with WHCP                                         | Yes           | No                     |
| WDK & HLK are primary vehicles for developing and certifying drivers| Yes           | Yes                    |
| Adhere to stricter reliability and serviceability requirements (e.g. driver package isolation)     | Yes           | No                     |


While it won't be required for a driver running only on Windows 10 Desktop to meet the additional requirements for a Windows Driver, doing so will enhance driver serviceability and reliability, as well as preparing the driver for possible future certification on Windows 10X.