---
title: Barcode scanner events
description: Describes the events that are passed from the device driver to the Point of Service (POS) API layer by using ReadFile.
ms.assetid: 'f0a7a525-8fea-4bce-a817-25c69cd47ddd'
ms.date: 09/07/2018
ms.localizationpriority: medium
---

# Barcode scanner events

This section describes the events that are passed from the device driver to the Point of Service (POS) API layer by using [ReadFile](/windows/win32/api/fileapi/nf-fileapi-readfile). This section focuses on events that are specific to barcode scanners.

## In this section

[BarcodeScannerDataReceived](barcodescannerdatareceived.md)  
Occurs after a successful scan event.

[BarcodeScannerErrorOccurred](barcodescannererroroccurred.md)  
Occurs when there is an error, such as a scanning error.

[BarcodeScannerImagePreviewReceived](barcodescannerimagepreviewreceived.md)  
Occurs when the device receives a bitmap image of the scan.

[BarcodeScannerTriggerPressed](barcodescannertriggerpressed.md)  
Occurs when the barcode scanner trigger is pressed.

[BarcodeScannerTriggerReleased](barcodescannertriggerreleased.md)  
Occurs when the barcode scanner trigger is released.