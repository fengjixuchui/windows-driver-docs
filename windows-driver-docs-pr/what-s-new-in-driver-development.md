---
title: What's new in driver development
description: This section describes new features for driver development in Windows 10.
ms.assetid: 5502AAF9-2400-4338-A646-C746B29F9A44
ms.date: 05/22/2020
ms.localizationpriority: medium
---

# <a name="top"></a>What's new in driver development

This section provides information about the new features and updates to Windows driver development in Windows 10.

## What's new in Windows 10, version 2004 (latest)

This section describes new features and updates for driver development in Windows 10, version 2004 (Windows 10 May 2020 Update).

### Windows Drivers

Windows 10, version 2004 is a transition release for universal drivers. In this release, universal drivers still exist, but are being replaced by Windows Drivers. A Windows Driver is a universal driver with a few additional requirements.

Windows Drivers are distinguished from Windows Desktop Drivers. While Windows Drivers run on Windows 10X and Windows 10 Desktop editions,  Windows Desktop Drivers run only on Windows 10 Desktop editions.

No changes are required to universal drivers for the version 2004 release, but documentation is available now so that you can plan ahead for upcoming changes.

For information about how to build, install, deploy, and debug a Windows Driver, see [Getting Started with Windows Drivers](https://docs.microsoft.com/windows-hardware/drivers/develop/getting-started-with-windows-drivers).

### Windows Hardware Error Architecture (WHEA)

WHEA includes a new interface (v2). For info about how to register as an error source and report errors, see [Using WHEA on Windows 10](whea/using-whea-on-windows-10.md).

### Display and Graphics Drivers

Several new and enhanced display and graphics driver features are available in Windows 10, version 2004, including D3D12 mesh shader support, sampler support, raytracing extensions, video motion estimation, and video protected resources support. See [What's New for Windows 10 Display and Graphics Drivers](https://docs.microsoft.com/windows-hardware/drivers/display/what-s-new-for-windows-10-display-and-graphics-drivers) for more details about these new features.

### Storage Drivers

A storage miniport driver can now get and set more information about a device's internal state, including the ability to reset a device. See [**IOCTL_STORAGE_GET_DEVICE_INTERNAL_LOG**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_get_device_internal_log) and [**StorPortHardwareReset**](https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storporthardwarereset) as good starting points.

### Windows Debugger

#### WinDbg Preview

Updates to [WinDbg Preview](https://docs.microsoft.com/windows-hardware/drivers/debugger/debugging-using-windbg-preview) to cover new features such as [WinDbg Preview - Timelines](https://docs.microsoft.com/windows-hardware/drivers/debugger/windbg-timeline-preview). Time travel timelines allows for the visualization of time travel code execution traces.

#### Stop Codes

- Updates to the [Bug Check Code Reference](https://docs.microsoft.com/windows-hardware/drivers/debugger/bug-check-code-reference2) topics and the addition of new parameters to topics such as [Bug Check 0x1A: MEMORY_MANAGEMENT](https://docs.microsoft.com/windows-hardware/drivers/debugger/bug-check-0x1a--memory-management) and [Bug Check 0xC4: DRIVER_VERIFIER_DETECTED_VIOLATION](https://docs.microsoft.com/windows-hardware/drivers/debugger/bug-check-0xc4--driver-verifier-detected-violation).

- New stop codes such as [Bug Check 0x1DA: HAL_BLOCKED_PROCESSOR_INTERNAL_ERROR](https://docs.microsoft.com/windows-hardware/drivers/debugger/bug-check-0x1da--hal-blocked-processor-internal-error), [Bug Check 0x1A2: WIN32K_CALLOUT_WATCHDOG_BUGCHECK](https://docs.microsoft.com/windows-hardware/drivers/debugger/bug-check-0x1a2--win32k-callout-watchdog-bugcheck) and  [Bug Check 0x119: VIDEO_SCHEDULER_INTERNAL_ERROR](https://docs.microsoft.com/windows-hardware/drivers/debugger/bug-check-0x119---video-scheduler-internal-error).

### Driver Security

Updates to the [Driver security checklist](https://docs.microsoft.com/windows-hardware/drivers/driversecurity/driver-security-checklist) to use the BinSkim tool.

## Related Topics

For information on what was new for drivers in past Windows releases, see the following pages:

* [Driver development changes for Windows 10, version 1903](driver-changes-for-windows-10-version-1903.md)
* [Driver development changes for Windows 10, version 1809](driver-changes-for-windows-10-version-1809.md)
* [Driver development changes for Windows 10, version 1803](driver-changes-for-windows-10-version-1803.md)
* [Driver development changes for Windows 10, version 1709](driver-changes-for-windows-10-version-1709.md)

[Back to Top](#top)

## Deprecated features

The following table describes Windows driver development features that have been removed in Windows 10.

| Driver technology | Feature | Deprecated in |
|---|---|---|
| GNSS/Location | [Geolocation driver sample for Windows 8.1](https://docs.microsoft.com/windows-hardware/drivers/gnss/sensors-geolocation-driver-sample) and related documentation | Windows 10, version 1709 |
| Mobile Operator Scenarios (Networking) | [AllowStandardUserPinUnlock](https://docs.microsoft.com/windows-hardware/drivers/mobilebroadband/allowstandarduserpinunlock) | Windows 10, version 1709 |
| Scan/Image | [WSD (Web Services for Devices) Challenger](https://docs.microsoft.com/windows-hardware/drivers/image/challenging-a-disconnected-scanner-with-the-wsd-challenger) functionality and related documentation | Windows 10, version 1709 |
|Mobile Operators| Mobile broadband app experience apps with Sysdev metadata packages are deprecated in favor of MO UWP APPS and COSA. | Windows 10, version 1803|
