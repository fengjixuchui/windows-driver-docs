---
title: Debugging a Universal Windows driver
description: Describes debugging techniques you can use with a Universal Windows driver.
ms.date: 06/09/2017
ms.localizationpriority: medium
---

# Debugging a Universal Windows driver

Starting in Windows 10, you can build your KMDF or UMDF driver binary so that it gets additional driver debugging information through the [Inflight Trace Recorder](https://docs.microsoft.com/windows-hardware/drivers/devtest/using-wpp-recorder). Universal Windows drivers can take advantage of this feature.

In addition, if you used the Visual Studio KMDF template, your driver uses Windows software trace preprocessor (WPP) to write trace messages. Your driver binary is an ETW provider with a provider GUID.

To send a trace message from your driver binary, use this code:

   ```cpp
   TraceEvents(TRACE_LEVEL_INFORMATION, TRACE_DRIVER, "%!FUNC! Entry");
   ```

You can access the ETW logs either using Tracelog via the [TShell tool](https://go.microsoft.com/fwlink/p/?linkid=617388) on a phone, or by using [!wmitrace](https://docs.microsoft.com/windows-hardware/drivers/debugger/wmi-tracing-extensions--wmitrace-dll-) in a debugger session.

To use Tracelog on a phone:

1. Establish a kernel-mode debugging session between a host computer and the phone.
2. On the host computer, in TShell, enter this command:

       ```cpp
       exec-device tracelog -addautologger MyLogger05 -guid c:\SteveGuid.txt -level 4 -flag 0xF –kd
       ```

3. Reboot the phone, and watch for trace messages in the debugger.

All existing kernel mode debug transports continue to work on Windows 10 for desktop editions. However, for both user-mode and kernel-mode driver binaries, you must use a remote debugger session over KDNET to test Windows 10 Mobile. For more info, see [Setting Up Kernel-Mode Debugging over a Network Cable Manually](https://docs.microsoft.com/windows-hardware/drivers/debugger/setting-up-a-network-debugging-connection) in Visual Studio.
