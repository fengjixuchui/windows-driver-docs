---
title: IPrinterScriptUsbWritePrintDataProgress ProcessedByteCount method (in)
description: Sets the number of bytes that the IHV JavaScript function has processed at the time this method was called.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 9E870B80-421B-496A-9510-D97D3A4D7892
keywords: ["ProcessedByteCount method Print Devices", "ProcessedByteCount method Print Devices , IPrinterScriptUsbWritePrintDataProgress interface", "IPrinterScriptUsbWritePrintDataProgress interface Print Devices , ProcessedByteCount method"]
topic_type:
- apiref
api_name:
- IPrinterScriptUsbWritePrintDataProgress.ProcessedByteCount
api_type:
- COM
ms.date: 07/07/2020
ms.localizationpriority: medium
---

# IPrinterScriptUsbWritePrintDataProgress::ProcessedByteCount method (in)

Sets the number of bytes that the IHV JavaScript function has processed at the time this method was called.

## Syntax

```cpp
HRESULT ProcessedByteCount(
  [in]  UINT32 value
);
```

## Parameters

*value* \[in\]  
The number of bytes processed at the time this method was called.

## Return valueS

This method returns an **HRESULT** value.

## Requirements

**Minimum supported client:** Windows 8.1

**Minimum supported server:** Windows Server 2012 R2

**Target platform:** Desktop

## See also

[**IPrinterScriptUsbWritePrintDataProgress**](iprinterscriptusbwriteprintdataprogress.md)
