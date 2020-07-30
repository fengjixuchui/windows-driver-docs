---
title: Provided WDTF Simple I/O plug-ins
description: Simple I/O plug-ins are extensions to the Windows Driver Test Framework (WDTF) that implement generic device-specific I/O functionality.
ms.assetid: 948E8CF5-24A1-4A7C-BD18-374F989AD053
ms.date: 04/20/2017
ms.localizationpriority: medium
---

# Provided WDTF Simple I/O plug-ins

Simple I/O plug-ins are extensions to the Windows Driver Test Framework (WDTF) that implement generic device-specific I/O functionality. If a plug-in exists for the type of device being tested, the [Device Fundamental tests](https://docs.microsoft.com/windows-hardware/drivers) use the WDTF Simple I/O interfaces to test I/O.

The following table shows the device types that have Simple I/O plug-ins. The table also indicates if there are specific requirements for testing the device. These are the same requirements you need to follow when you use the [Windows Hardware Certification Kit (HCK)](https://go.microsoft.com/fwlink/p/?linkid=254893).

If your device type is not listed, you can create one, see [How to customize I/O for your device using the WDTF Simple I/O Action Plug-in](to-customize-i-o-for-your-device-using-the-wdtf-simple-i-o-action-plug-in.md)

## Provided Simple I/O plugins and device requirements for testing and tips for troubleshooting

The following section lists the device types that have Simple I/O plug-ins. The section also indicates if there are specific requirements for testing the device. These are the same requirements you need to follow when you use the [Windows Hardware Certification Kit (HCK)](https://go.microsoft.com/fwlink/p/?linkid=254893). The section also shows tips you can use to troubleshoot and triage test failures.

* [Audio devices](#audio)
* [Bluetooth devices](#bluetooth)
* [CDROM devices](#cdrom)
* [Disk devices](#disk)
* [Display devices](#display)
* [GPS devices](#gps-devices-and-gps-devices-in-systems)
* [LAN devices](#lan)
* [Mobile Broadband devices](#mobile-broadband)
* [Portable devices](#portable-devices)
* [Smart Card Readers](#smart-card-readers)
* [Sensor devices](#sensors)
* [Volume](#volume)
* [Webcam](#webcam)
* [WLAN](#wlan)
* [USB Controller and HUB with Mutt](#usb-controller-and-hub-with-mutt)

For a list of Device Fundamental tests that have specific requirements, see [Device Fundamental tests that have specific device configuration requirements](#device-fundamental-tests-that-have-specific-device-configuration-requirements)

### Audio

#### Requirements

* Device must have at least one render type endpoint connected (speakers, headphones, etc.).

* If the targeted audio device has HDMI video and audio output capability, to perform audio tests, the device must be connected to an HDMI audio capable device such as an HDMI Monitor or an A/V Receiver.

#### Type of I/O plug-in performs

* Plays a sine tune on render type endpoint. Captures audio on a capture type endpoint.

#### How to triage test failures

* Look at failing HRESULT to perform initial triage.
* If test is not responding, use the kernel debugger on the target computer to narrow down the root-cause.
* Run traces:
  * Start kernel traces:

```syntax
xperf.exe -on LOADER+PROC_THREAD+CSWITCH+DISK_IO+HARD_FAULTS+PROFILE+INTERRUPT+NETWORKTRACE+DPC+Latency+POWER -stackwalk ProcessCreate+ProcessDelete+ImageLoad+ImageUnload+ThreadCreate+ThreadDelete+CSwitch+ReadyThread+Profile+DiskFlushInit+FileFlush+RegFlush+HardFault+VirtualAlloc+VirtualFree -BufferSize 1024 -MinBuffers 512 -MaxBuffers 1024 -f Audio_SimpleIo_Kernel.etl
```

  * Start audio traces:

```syntax
xperf.exe -start AudioSimpleIo -on Microsoft-Windows-Audio+a6a00efd-21f2-4a99-807e-9b3bf1d90285:0xffff:0x3 -BufferSize 1024 -MinBuffers 512 -MaxBuffers 1024 -f Audio_SimpleIo.etl
```

  * Run tests.
  * Stop traces:

```syntax
xperf.exe -stop "NT Kernel Logger" Audio_SimpleIo
```

  * Merge traces:

```syntax
xperf.exe -merge Audio_SimpleIo_Kernel.etl Audio_SimpleIo.etl Audio_SimpleIo _Merged.etl
```

  * View the merged trace file with Xperf (**xperfview**).

### Bluetooth

#### Requirements

* No special requirements.

#### Type of I/O plug-in performs

* Uses [**BluetoothFindFirstDevice function**](https://docs.microsoft.com/windows/desktop/api/bluetoothapis/nf-bluetoothapis-bluetoothfindfirstdevice) to find a Bluetooth device.

### CDROM

#### Requirements

* Drive letter is assigned.
* Media is present in the device.
* Files are present on the media inserted.

#### Type of I/O plug-in performs

* Finds files on the CD-ROM and performs read operation using the Win32 [**ReadFile**](https://docs.microsoft.com/windows/desktop/api/fileapi/nf-fileapi-readfile) API.

#### How to triage test failures

* On the test computer, navigate to the CD/DVD drive in question and confirm you can access the contents of the drives.
* The CD-Rom Simple I/O plug-in searches for files on CD/DVD to use to perform reads from. Ensure the CD/DVD has files encoded on disk.
* This Simple I/O plug uses the Win32 [**CreateFile**](https://docs.microsoft.com/windows/desktop/api/fileapi/nf-fileapi-createfilea), [**WriteFile**](https://docs.microsoft.com/windows/desktop/api/fileapi/nf-fileapi-writefile), [**ReadFile**](https://docs.microsoft.com/windows/desktop/api/fileapi/nf-fileapi-readfile) functions. Error returned are most likely Win32 error codes from these APIs.

### Disk

#### Requirements

* Disk has at least one associated volume Drive letter is assigned.

#### Type of I/O plug-in performs

* Uses the Simple I/O plug-in for [Volumes](#volume).

### Display

#### Requirements

* No special requirements for testing.

#### Type of I/O plug-in performs

* Uses D3DX APIs to exercise graphics adapter.

#### How to triage test failures

* Look through the test logs, which report failures from the APIs that are used.

### GPS devices (and GPS devices in systems)

#### Requirements

* The device must be tested in a location with proper GPS signals.

#### Type of I/O plug-in performs

* Uses the I/O plug-in for [Sensors](#sensors).

### LAN

#### Requirements

* Device has an IPv6 address.

* Device has an IPv6 gateway address (otherwise the WDTFREMOTESYSTEM parameter should be passed to the test with an IPv6 address that the test NIC can ping).

* The network operation status of the device is IfOperStatusUp.

* Network device is not a WWAN or a WLAN device.

#### Type of I/O plug-in performs

* Pings IPv6 network gateway address.

#### How to triage test failures

* Confirm that there is an existing IP address.
* Confirm that there is a gateway IPv6 IP Address.
* Confirm the IP gateway address manually (use ping.exe).

### Mobile broadband

#### Requirements

* No special requirements for testing.

#### Type of I/O plug-in performs

* Uses [**IMbnInterface interface**](https://docs.microsoft.com/windows/desktop/api/mbnapi/nn-mbnapi-imbninterface) and calls GetHomeProvider, [**IMbnInterface::GetInterfaceCapability method**](https://docs.microsoft.com/windows/desktop/api/mbnapi/nf-mbnapi-imbninterface-getinterfacecapability), and [**IMbnInterface::GetReadyState method**](https://docs.microsoft.com/windows/desktop/api/mbnapi/nf-mbnapi-imbninterface-getreadystate) APIs to exercise the device.

#### How to triage test failures

* The MobileBroadbandPlugin has limited areas it can fail.

  * "MobileBroadbandPlugin: Getting all Mobile Broadband interfaces returned failure."
  * "MobileBroadbandPlugin: Getting the interface returned failure."
  * "MobileBroadbandPlugin: Getting the DeviceId returned."
  * "MobileBroadbandPlugin: Getting the interface capabilities returned failure"
  * "MobileBroadbandPlugin: Getting the ReadyState returned failure."

* The best place to investigate the failure is starting from the device and determine if it was unable to indicate Ready Information or Device Capabilities. To debug further OS Trace file need to be collected.

  * Run the command: **netsh trace start wwan\_dbg**
  * Reproduce the issue.
  * Run the command: **netsh trace stop**

### Portable devices

#### Requirements

* Device has a storage component where folders and files can be created.

**Type of I/O plug-in performs:**

* Reads and writes a file to the storage component on WPD device using WPD APIs.

### Smart card readers

#### Requirements

* Device has Athena T0 test card inserted.

#### Type of I/O plug-in performs

* Reads and writes data to Athena T0 card inserted in the card reader.

### Sensors

#### Requirements

* The GPS device must be tested in a location with proper GPS signals.

### Volume

#### Requirements

* Volume has a drive letter assigned.
* Volume has 5MB of free space.
* Volume is not write-protected.
* Media is present in the device.

#### Type of I/O plug-in performs

* Creates a directory called WDTF\_Volume\_IO and creates a file called SimpleIO.tmp. The I/O is performed by calling [**ReadFile**](https://docs.microsoft.com/windows/desktop/api/fileapi/nf-fileapi-readfile) and [**WriteFile**](https://docs.microsoft.com/windows/desktop/api/fileapi/nf-fileapi-writefile) APIs to this file.

#### How to triage test failures

* On the test computer, navigate to the drive in question and confirm you can access the contents of the drive.
* Attempt to save a file to the drive. Ensure you can save and access it readily.
* This Simple I/O plug uses the Win32 [**CreateFile**](https://docs.microsoft.com/windows/desktop/api/fileapi/nf-fileapi-createfilea), [**WriteFile**](https://docs.microsoft.com/windows/desktop/api/fileapi/nf-fileapi-writefile), [**ReadFile**](https://docs.microsoft.com/windows/desktop/api/fileapi/nf-fileapi-readfile) functions. Error returned are most likely Win32 error codes from these APIs.

### Webcam

#### Requirements

* No special requirements for testing.

    > [!NOTE]
    > The Simple I/O plug-in for webcam devices has a dependency on the MFPlat.dll file, which is not available on versions of Windows that do not include Media Player and related technologies, for example Windows 7 N or Windows 7 KN. On these version of Windows, the Media Feature Pack must be installed. The Media Feature Pack is available for download. For more information, see [KB Article 968211](https://go.microsoft.com/fwlink/p/?linkid=266437).

**Type of I/O plug-in performs:**

* Uses Media Foundation interfaces to capture video.

### WLAN

#### Requirements

* See [Troubleshooting WLAN SimpleIO plugin failures that are logged by Device Fundamentals tests](https://go.microsoft.com/fwlink/p/?linkid=309556) in the HCK documentation.

#### Type of I/O plug-in performs

* See [Troubleshooting WLAN SimpleIO plugin failures that are logged by Device Fundamentals tests](https://go.microsoft.com/fwlink/p/?linkid=309556) in the HCK documentation.

#### How to triage test failures

* See [Troubleshooting WLAN SimpleIO plugin failures that are logged by Device Fundamentals tests](https://go.microsoft.com/fwlink/p/?linkid=309556) in the HCK documentation.

### USB Controller and HUB with Mutt

#### Requirements

* No special requirements for testing.

    Device has a Symbolic link.

#### Type of I/O plug-in performs

* USB transfer tests using the Microsoft USB Test Tool (MUTT) device. Transfer types covered are control, bulk, isochronous, interrupt, and streams (only if SuperMUTT is plugged into USB 3.0 controller)

#### How to triage test failures

* Start by examining the messages in the test log files.
* Further investigate by enabling Event Tracing for Windows (ETW) on the USB 2.0 and USB 3.0 stacks.
  * For USB 2.0, see Microsoft Windows USB Core Team Blog - [ETW in the Windows 7 USB core stack](https://go.microsoft.com/fwlink/p/?linkid=266442)
  * For USB 3.0, see the Microsoft Windows USB Core Team Blog - [How to Capture and Read USB ETW Traces in Windows 8]( https://go.microsoft.com/fwlink/p/?linkid=266443)

## Device Fundamental tests that have specific device configuration requirements

Before you run the following [Device Fundamental tests](https://docs.microsoft.com/windows-hardware/drivers), the devices on the test computer must be configured according to the requirements described for the specific device types. See the list of [the provided Simple I/O plug-ins and device requirements.](#provided-simple-io-plugins-and-device-requirements-for-testing-and-tips-for-troubleshooting)

* PCI Root Port Surprise Remove Test (PCI devices only)
* Device Path Exerciser Test (Certification)
* Sleep and PNP (disable and enable) with IO Before and After (Certification)
* Plug and Play Driver Test (Certification)
* Concurrent Hardware And Operating System (CHAOS) Test (Certification)
* Reinstall with IO Before and After (Certification)
* Device Install Check For File System Consistency (Certification)
* Device Install Check For Other Device Stability (Certification)

## Related topics

[Device Fundamentals Tests](https://docs.microsoft.com/windows-hardware/drivers/devtest/device-fundamentals-tests)  
[How to How to test a driver at runtime using Visual Studio](https://docs.microsoft.com/windows-hardware/drivers)  
[How to How to test a driver at runtime from a Command Prompt](https://docs.microsoft.com/windows-hardware/drivers)  
[How to select and configure the Device Fundamentals tests](https://docs.microsoft.com/windows-hardware/drivers)  
[Troubleshooting the Device Fundamentals tests](https://docs.microsoft.com/windows-hardware/drivers)  
