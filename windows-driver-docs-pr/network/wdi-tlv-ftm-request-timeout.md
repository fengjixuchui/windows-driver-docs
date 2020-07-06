---
title: WDI_TLV_FTM_REQUEST_TIMEOUT
description: WDI_TLV_FTM_REQUEST_TIMEOUT is a TLV that contains the maximum time, in milliseconds, to complete a Fine Timing Measurement (FTM).
ms.assetid: C2C4CDEE-4CB6-49C1-8DBF-4A1AE71954ED
ms.date: 02/15/2019
keywords:
 - WDI_TLV_FTM_REQUEST_TIMEOUT Network Drivers Starting with Windows Vista
ms.localizationpriority: medium
ms.custom: 19H1
---

# WDI_TLV_FTM_REQUEST_TIMEOUT

**WDI_TLV_FTM_REQUEST_TIMEOUT** is a TLV that contains the maximum time, in milliseconds, to complete a Fine Timing Measurement (FTM).

This TLV is used in the task parameters of [OID_WDI_TASK_REQUEST_FTM](oid-wdi-task-request-ftm.md).

## TLV Type

0x161

## Length

The size (in bytes) of a UINT32.

## Values

| Type | Description |
| --- | --- |
| UINT32 | The maximum time, in milliseconds, to complete the FTM. The timeout is set to 150 ms multiplied by the number of targets. |

## Requirements

**Minimum supported client**: Windows 10, version 1903
**Minimum supported server**: Windows Server 2016
**Header**: Wditypes.hpp
