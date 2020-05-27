---
title: Driver development changes for Windows 10, version 1903
description: This section describes new features for driver development in Windows 10.
ms.assetid: 90f7754d-be7a-408d-8b89-b173a86c4fa3
ms.date: 04/28/2020
ms.localizationpriority: medium
---

# What's new in Windows 10, version 1903

This section describes new features and updates for driver development in Windows 10, version 1903 (Windows 10 April 2019 Update).

## <a name="audio-1903"></a>Audio

The following is a list of new and updated Audio features in Windows 10, version 1903:

* New reference topics on the Audio OEM Adapter used for Voice Activation in the new [eventdetectoroemadapter.h](https://docs.microsoft.com/windows-hardware/drivers/ddi/eventdetectoroemadapter/) header.
* New Far Field Audio information: 
    * [PKEY_Devices_AudioDevice_Microphone_IsFarField](https://docs.microsoft.com/windows-hardware/drivers/audio/pkey-devices-audiodevice-microphone-isfarfield)
    * [KSPROPSETID_InterleavedAudio](https://docs.microsoft.com/windows-hardware/drivers/audio/kspropsetid-interleavedaudio)
    * [KSPROPERTY_INTERLEAVEDAUDIO_FORMATINFORMATION](https://review.docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-interleavedaudio-formatinformation)
    
* New jack description information in [USB Audio 2.0 Drivers](https://docs.microsoft.com/windows-hardware/drivers/audio/usb-2-0-audio-drivers).

## <a name="camera-1903"></a>Camera

New Camera driver documentation and features added in Windows 10, version 1903 include:

* New [IR Torch](https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-cameracontrol-extended-irtorchmode) extended property control to set an IR camera's infrared torch power level and duty cycle.
* New [KSCATEGORY_NETWORK_CAMERA](https://docs.microsoft.com/windows-hardware/drivers/install/kscategory-network-camera) device.
* New and updated [USB Video Class (UVC) 1.5 extension](https://docs.microsoft.com/windows-hardware/drivers/stream/uvc-extensions-1-5) documentation for the following control selectors:
  * MSXU_CONTROL_FACE_AUTHENTICATION
  * MSXU_CONTROL_METADATA
  * MSUX_CONTROL_IR_TORCH


## Debugging

Changes to the Debugger for Windows 10, version 1903 include the following:

* New stop codes were added to allow better tracking on unique failure types in the Windows operating system. In addition a number of existing bug check topics were expanded and updated. For more information, see [Bug Check Code Reference](https://docs.microsoft.com/windows-hardware/drivers/debugger/bug-check-code-reference2).

* Updates to KDNET topics to improve ease of use, for example in new [Setting Up KDNET Network Kernel Debugging Automatically](https://docs.microsoft.com/windows-hardware/drivers/debugger/setting-up-a-network-debugging-connection-automatically)

* Updates to IP V6 KDNET support.

* New [JavaScript Debugging](https://docs.microsoft.com/windows-hardware/drivers/debugger/javascript-debugger-scripting) topic

## <a name="display-1903"></a>Display

Updates to Display driver development in Windows 10, version 1903 include the following:

* **Super Wet Ink** New DDIs were added to enable front buffer rendering. See [D3DWDDM2_6DDI_SCANOUT_FLAGS](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3dwddm2_6ddi_scanout_flags) and [PFND3DWDDM2_6DDI_PREPARE_SCANOUT_TRANSFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3dwddm2_6ddi_prepare_scanout_transformation).

* **Variable Rate Shading** Enables allocation of rendering performance/power at varying rates across rendered images. See [PFND3D12DDI_RS_SET_SHADING_RATE_0062](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d12umddi/nc-d3d12umddi-pfnd3d12ddi_rs_set_shading_rate_0062) and [D3D12DDI_SHADING_RATE_0062](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d12umddi/ne-d3d12umddi-d3d12ddi_shading_rate_0062).

* **Collect Diagnostic Info** Allows the OS to collect a private data from drivers for graphics adapters which consist of both rendering and display functions. See [DXGKDDI_COLLECTDIAGNOSTICINFO](https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_collectdiagnosticinfo).

* **Background Processing** Allows user mode drivers to express desired threading behavior, and the runtime to control/monitor it. User mode drivers would spin up background threads and assign the threads as low a priority as possible, and rely on the NT scheduler to ensure these threads don’t disrupt the critical-path threads, generally with success. See [PFND3D12DDI_QUEUEPROCESSINGWORK_CB_0062](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d12umddi/nc-d3d12umddi-pfnd3d12ddi_queueprocessingwork_cb_0062).

* **Driver Hot Update** Reduce server downtime as much as possible when an OS component needs to be updated. See [DXGKDDI_SAVEMEMORYFORHOTUPDATE](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkcb_savememoryforhotupdate) and [DXGKDDI_RESTOREMEMORYFORHOTUPDATE](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_restorememoryforhotupdate).

## <a name="networking-1903"></a>Networking

## NetAdapterCx

In the NetAdapter WDF class extension (NetAdapterCx), Net ring buffers have been replaced by Net rings, which have a new interface for sending and receiving network data using net ring iterators. The following is a list of new topics:

* [Introduction to net rings](https://docs.microsoft.com/windows-hardware/drivers/netcx/introduction-to-net-rings)
* [Sending network data with net rings](https://docs.microsoft.com/windows-hardware/drivers/netcx/sending-network-data-with-net-rings) with a new animation that illustrates how to send data
* [Receiving network data with net rings](https://docs.microsoft.com/windows-hardware/drivers/netcx/receiving-network-data-with-net-rings) with a new animation that illustrates how to receive data
* [Canceling network data with net rings](https://docs.microsoft.com/windows-hardware/drivers/netcx/canceling-network-data-with-net-rings)

New headers that support this feature include the following:

* [Ring.h](https://docs.microsoft.com/windows-hardware/drivers/ddi/ring/index)
* [Ringcollection.h](https://docs.microsoft.com/windows-hardware/drivers/ddi/ringcollection/index)
* [Netringiterator.h](https://docs.microsoft.com/windows-hardware/drivers/ddi/netringiterator/index)

The following is a list of NetAdapterCx content updates:

* Default adapter objects have been removed in favor of a single adapter object type. The following topics have been updated accordingly:

  * [Summary of NetAdapterCx objects](https://docs.microsoft.com/windows-hardware/drivers/netcx/summary-of-netadaptercx-objects)
  * [Device and adapter initialization](https://docs.microsoft.com/windows-hardware/drivers/netcx/device-and-adapter-initialization)

* Hardware offload and packet extension DDIs have been reorganized into new headers:

  * [Checksum.h](https://docs.microsoft.com/windows-hardware/drivers/ddi/checksum/index)
  * [Checksumtypes.h](https://docs.microsoft.com/windows-hardware/drivers/ddi/checksumtypes/index)
  * [Extension.h](https://docs.microsoft.com/windows-hardware/drivers/ddi/extension/index)
  * [Lso.h](https://docs.microsoft.com/windows-hardware/drivers/ddi/lso/index)
  * [Lsotypes.h](https://docs.microsoft.com/windows-hardware/drivers/ddi/lsotypes/index)
  * [Rsc.h](https://docs.microsoft.com/windows-hardware/drivers/ddi/rsc/index)
  * [Rsctypes.h](https://docs.microsoft.com/windows-hardware/drivers/ddi/rsctypes/index)

* Fundamental networking data structures, packets and fragments, have been updated and put into new headers:

  * [Packet.h](https://docs.microsoft.com/windows-hardware/drivers/ddi/packet/index)
  * [Fragment.h](https://docs.microsoft.com/windows-hardware/drivers/ddi/fragment/index)

* Overhauled [Transmit and receive queues](https://docs.microsoft.com/windows-hardware/drivers/netcx/transmit-and-receive-queues) topic to include callback samples and major operations for packet queues.

## Mobile operator scenarios

New Mobile Plans content for mobile operators to sell plans to customers directly on Windows 10 devices, through the Mobile Plans app:

* [Mobile Plans](https://docs.microsoft.com/windows-hardware/drivers/mobilebroadband/mobile-plans)

## <a name="mobilebroadband-1903"></a>Mobile broadband

The following features were added to Mobile broadband in Windows 10, version 1903:

* New [SIM card (UICC) file/application system access](https://docs.microsoft.com/windows-hardware/drivers/network/mb-uicc-application-and-file-system-access) feature
* New [Cellular Time Information (NITZ)](https://docs.microsoft.com/windows-hardware/drivers/network/mb-nitz-support) feature.
* New [modem logging with DSS](https://docs.microsoft.com/windows-hardware/drivers/network/mb-modem-logging-with-dss) feature.
* New [5G data class support](https://docs.microsoft.com/windows-hardware/drivers/network/mb-5g-data-class-support) feature.

## Power Management Framework

The power management framework (PoFx) enables a driver to define one or more sets of individually adjustable performance states for individual components within a device. The driver can use performance states to throttle a component's workload to provide just enough performance for its current needs. For more information, see [Component-Level Performance State Management](https://docs.microsoft.com/windows-hardware/drivers/kernel/component-level-performance-management).

Windows 10, version 1903 includes support for the [Directed Power Management Framework (DFx)](https://docs.microsoft.com/windows-hardware/drivers/kernel/introduction-to-the-directed-power-management-framework).  Related reference documentation includes the following:

* [PO_FX_DEVICE_V3](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-po_fx_device_v3)
* [PO_FX_DIRECTED_POWER_DOWN_CALLBACK callback function](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_directed_power_down_callback)
* [PO_FX_DIRECTED_POWER_UP_CALLBACK callback function](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_directed_power_up_callback)
* [PoFxCompleteDirectedPowerDown](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxcompletedirectedpowerdown) function

For information about testing for DFx, please see the following pages:

* [Directed FX Single Device Test](https://docs.microsoft.com/windows-hardware/test/hlk/testref/34cfdfa6-7826-443c-9717-bc28c3166092)
* [Directed FX System Verification Test](https://docs.microsoft.com/windows-hardware/test/hlk/testref/def16163-9118-4d4a-b559-37873befa12e)
* [PwrTest DirectedFx Scenario](devtest/pwrtest-directedfx-scenario.md)

## <a name="print-1903"></a>Print

New Print driver documentation and features added in Windows 10, version 1903 include:

* New USB print IOCTLs:

  * [IOCTL_USBPRINT_GET_INTERFACE_TYPE](https://docs.microsoft.com/windows-hardware/drivers/ddi/usbprint/ni-usbprint-ioctl_usbprint_get_interface_type)
  * [IOCTL_USBPRINT_GET_PROTOCOL](https://docs.microsoft.com/windows-hardware/drivers/ddi/usbprint/ni-usbprint-ioctl_usbprint_get_protocol)
  * [IOCTL_USBPRINT_SET_PROTOCOL](https://docs.microsoft.com/windows-hardware/drivers/ddi/usbprint/ni-usbprint-ioctl_usbprint_set_protocol)

* New **fpRegeneratePrintDeviceCapabilities** [PRINTPROVIDER](https://docs.microsoft.com/windows-hardware/drivers/ddi/winsplp/ns-winsplp-_printprovidor) structure member and updated documentation.

## <a name="sensors-1903"></a>Sensors

New features in sensor driver development in Windows 10, version 1903 include a [MALT (Microsoft Ambient Light Tool) tool](https://docs.microsoft.com/windows-hardware/drivers/sensors/testing-malt-building-a-light-testing-tool) for testing and calibrating screen brightness.

There were also updates to the Ambient Color OEM whitepaper.

## <a name="storage-1903"></a>Storage

The following Storage features were added in Windows 10, version 1903:

* New Storport APIs for logging device failure and hardware protocol errors in ETW events and to query for platform D3 desired behavior
* New API to set the properties of a storage device or adapter
* For file systems, new DDIs were added to support retrieving extended attributes (EA) information upon create completion, allowing mini-filters to alter the ECP payload to change what higher filters see

## Windows Driver Frameworks (WDF)

In Windows 10, version 1903, the Windows Driver Framework (WDF) includes Kernel-Mode Driver Framework (KMDF) version 1.29 and User-Mode Driver Framework (UMDF) version 2.29.

For info on what's included in these framework versions, see [What's New for WDF Drivers in Windows 10](https://docs.microsoft.com/windows-hardware/drivers/wdf/).
To see what was added in previous versions of WDF, see [KMDF Version History](https://docs.microsoft.com/windows-hardware/drivers/wdf/kmdf-version-history) and [UMDF Version History](https://docs.microsoft.com/windows-hardware/drivers/wdf/umdf-version-history).

## Windows Hardware Error Architecture (WHEA)

Windows 10, version 1903 includes a simplified interface to WHEA.  For more info, see the following pages:

* [**WheaAddErrorSourceDeviceDriver**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-wheaadderrorsourcedevicedriver)
* [**WheaReportHwErrorDeviceDriver**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-wheareporthwerrordevicedriver)
* [**WheaRemoveErrorSourceDeviceDriver**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-whearemoveerrorsourcedevicedriver)
* [**WHEA_ERROR_SOURCE_CONFIGURATION_DEVICE_DRIVER**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-whea_error_source_configuration_device_driver)
* [*WHEA_ERROR_SOURCE_READY_DEVICE_DRIVER*](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nc-ntddk-_whea_error_source_ready_device_driver)
* [*WHEA_ERROR_SOURCE_UNINITIALIZE_DEVICE_DRIVER*](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nc-ntddk-_whea_error_source_uninitialize_device_driver)
* [*WHEA_ERROR_SOURCE_INITIALIZE_DEVICE_DRIVER*](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nc-ntddk-_whea_error_source_initialize_device_driver)

## <a name="wifi-1903"></a>Wi-fi

New Wi-fi driver development documentation and features include:

* New Fine Timing Measurement (FTM) feature
* New [WPA3-SAE Authentication](https://docs.microsoft.com/windows-hardware/drivers/network/wpa3-sae-authentication) feature
* New Multiband Operation (MBO) support to improve roaming performance in enterprise scenarios
* New beacon report offloading support
* For OID commands, NDIS status indications, and TLVs for these new features, see [WDI doc change history](https://docs.microsoft.com/windows-hardware/drivers/network/wdi-doc-change-history)

The following topics were updated for Windows 10, version 1903:

* [WDI_AUTH_ALGORITHM](https://docs.microsoft.com/windows-hardware/drivers/ddi/wditypes/ne-wditypes-_wdi_auth_algorithm) - added support for WPA3-SAE authentication
* [OID_WDI_TASK_P2P_SEND_REQUEST_ACTION_FRAME](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wdi-task-p2p-send-request-action-frame) and [OID_WDI_TASK_P2P_SEND_RESPONSE_ACTION_FRAME](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wdi-task-p2p-send-response-action-frame) - added additional validation of outgoing Point to Point (P2P) action frames